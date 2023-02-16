# 09 CRUD

## 2023-02-16

### Agenda

- CRUD
- HTTP methods
- Rudimentary implementation of CRUD in NodeJS

### Slides

https://docs.google.com/presentation/d/1p9KxQ5hs6O-OS7xldBTZY6tWSBQFxNz8rrY3sQaTmFU/edit?usp=sharing

### Useful resources

#### CRUD

[CRUD](https://developer.mozilla.org/en-US/docs/Glossary/CRUD) - MDN web docs

[What is CRUD?](https://portal-app.production-eks.codecademy.com/article/what-is-crud) - CodeAcademy

[CRUD (create, read, update and delete) - defninition and overview](https://www.sumologic.com/glossary/crud/) - SumoLogic

[REST vs. CRUD](https://www.logicmonitor.com/blog/rest-vs-crud) - Logic Monitor

#### HTTP Methods

[Using HTTP methods for RESTful services](https://www.restapitutorial.com/lessons/httpmethods.html) - REST API Tutorial

[Which HTTP methids match up to which CRUD methods?](https://stackoverflow.com/questions/6203231/which-http-methods-match-up-to-which-crud-methods) - StackOverflow post

[CRUD mapping to HTTP verbs](https://medium.com/@ritika.atal.work/crud-mapping-to-http-verbs-354a3c0009f5) - Ritka Atal

[Using HTTP Methods: CRUD Operations](https://www.studytonight.com/rest-web-service/using-http-methods) - Study Tonight

#### CRUD and NodeJS

[How to Build a CRUD Command Line Application With Node.js](https://www.freecodecamp.org/news/how-to-build-a-command-line-application-with-nodejs/) - Njoku Samson Ebere

[Build a CRUD App With Only JSON Files Using a Node.js API](https://adevait.com/nodejs/build-a-crud-app-with-only-json-files) - Uma Victor

> In the above link, you will not need to use the `body-parser` package, as this middleware is now built into Express.js.

### Notes

What routes? 

/api/

/api/users/ GET all users

SELECT all records in entire user table.

/api/users/register/ POST username, email address

If no data sent, return error

Else, INSERT record with username, email address, etc. in user table

URLEncoded data
JSON body

/api/users/ID/ GET one user by ID

If ID doesn't exist, then return an error

Else, SELECT ID record from the user table

/api/users/replace/ID/ PUT one user info in place of same



/api/users/update/ID/ PATCH one user info to update a key 

If ID doesn't exist, then return an error

Else, UPDATE ID record from the user table with whatever key

URLEncoded
JSON

/api/users/delete/ID/ DELETE one user record from user data

If ID doesn't exist, then return an error

Else, DELETE ID record from user table
