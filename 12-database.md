# 12 Database

## 2023-02-28

### Agenda

1. Create database for arbitrary data
2. Create endpoint to send arbitrary data to DB
3. Read data through endpoint
3. Update data through endpoint
4. Delete data through endpoint

### Useful links

#### User endpoints

[Build a REST API with Node.js SQLite and Express JS](https://developerhowto.com/2018/12/29/build-a-rest-api-with-node-js-and-express-js/)

#### General database integration

[Express Database Integration Guide](https://expressjs.com/en/guide/database-integration.html)

[Database integration in Express](https://www.geeksforgeeks.org/database-integration-in-express-js/)

#### SQLite3

[better-sqlite3 API documentation](https://github.com/JoshuaWise/better-sqlite3/blob/master/docs/api.md)

[better-sqlite3](https://www.npmjs.com/package/better-sqlite3) - NPM

[SQLite3 data types](https://www.sqlite.org/datatype3.html)

### Notes

Below is the database service script that we will work with in class today:

```database.js
// Require better-sqlite3.
const Database = require('better-sqlite3');

// Connect to a database or create one if it doesn't exist yet.
const db = new Database('app.db');

// Is the database initialized or do we need to initialize it?
const stmt = db.prepare(`
    SELECT name FROM sqlite_master WHERE type='table' and name='userinfo';`
    );
// Define row using `get()` from better-sqlite3
let row = stmt.get();
// Check if there is a table. If row is undefined then no table exists.
if (row === undefined) {
// Echo information about what you are doing to the console.
    console.log('Your userinfo table appears to be empty. Initializing it now.');
// Set a const that will contain your SQLlite commands to initialize the userinfo talbe.
    const sqlInit = `
        CREATE TABLE userinfo ( id INTEGER PRIMARY KEY, username VARCHAR, password VARCHAR, email VARCHAR );
        INSERT INTO userinfo (username, password) VALUES ('user1','supersecurepassword','user1@email.unc.edu'),('test','anotherpassword','test@somehost.com');
    `;
// Execute SQL commands that we just wrote above.
    db.exec(sqlInit);
// Echo information about what we just did to the console.
    console.log('userinfo table created in app.db.');
} else {
// Since the database already exists, echo that to the console.
    console.log('userinfo table check passed.')
}
// Export all of the above as a module so that we can use it elsewhere.
module.exports = db
```

And the server script with the endpoint definitions we demoed in class is included below:

```server.js
// Define app using express
var express = require("express")
var app = express()
// Require database SCRIPT file
const db = require("./database.js")
// Require md5 MODULE
//var md5 = require("md5")
// Make Express use its own built-in body parser for both urlencoded and JSON body data.
app.use(express.urlencoded({ extended: true }));
app.use(express.json());

// Server port
var HTTP_PORT = 5000 
// Start server
const server = app.listen(HTTP_PORT, () => {
    console.log("Server running on port %PORT%".replace("%PORT%",HTTP_PORT))
});
// READ (HTTP method GET) at root endpoint /app/
app.get("/app/", (req, res, next) => {
    res.json({"message":"Your API works! (200)"});
	res.status(200);
});

// Define other CRUD API endpoints using express.js and better-sqlite3
// CREATE a new user (HTTP method POST) at endpoint /app/new/
app.post("/app/new/user", (req, res, next) => {
    let data = {
        user: req.body.username,
        pass: req.body.password
    }
    const stmt = db.prepare('INSERT INTO userinfo (username, password) VALUES (?, ?)')
    const info = stmt.run(data.user, data.pass)
    res.status(200).json(info)
});
// READ a list of users (HTTP method GET) at endpoint /app/users/
app.get("/app/users", (req, res) => {	
    try {
        const stmt = db.prepare('SELECT * FROM userinfo').all()
        res.status(200).json(stmt)
    } catch {
        console.error(e)
    }
});

// READ a single user (HTTP method GET) at endpoint /app/user/:id
app.get("/app/user/:id", (req, res) => {
    try {
        const stmt = db.prepare('SELECT * FROM userinfo WHERE id = ?').get(req.params.id);
        res.status(200).json(stmt)
    } catch (e) {
        console.error(e)
    }

});

// UPDATE a single user (HTTP method PATCH) at endpoint /app/update/user/:id
app.patch("/app/update/user/:id", (req, res) => {
    let data = {
        user: req.body.username,
        pass: req.body.password
    }
    const stmt = db.prepare('UPDATE userinfo SET username = COALESCE(?,username), password = COALESCE(?,password) WHERE id = ?')
    const info = stmt.run(data.user, data.pass, req.params.id)
    res.status(200).json(info)
});

// DELETE a single user (HTTP method DELETE) at endpoint /app/delete/user/:id
app.delete("/app/delete/user/:id", (req, res) => {
    const stmt = db.prepare('DELETE FROM userinfo WHERE id = ?')
    const info = stmt.run(req.params.id)
    res.status(200).json(info)
});
// Default response for any other request
app.use(function(req, res){
	res.json({"message":"Endpoint not found. (404)"});
    res.status(404);
});

process.on('SIGTERM', () => {
    server.close(() => {
        console.log('Server stopped.')
    })
})
```

#### Questions

1. What are some ways to improve this process?
2. What is missing?
3. Think about the mechanisms required to make use of this in the context of creating and maintaining a userbase for authentication and authorization. What pieces (other endpoints, middleware, etc.) will we need to incorporate later this week and next week to make that possible? 

