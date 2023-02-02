# 06 Manipulating Data

## 2023-02-02

### Agenda

- Objects
- Prototypes
- Reading and Writing JSON to file
- Parsing JSON
- JSON Stringify

# Slides



### Useful resources

#### Objects and JSON

[Introducing JavaScript Objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects) - MDN

[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) - MDN

[JavaScript Objects](https://www.w3schools.com/js/js_object_definition.asp) - w3schools

[JSON Intro](https://www.w3schools.com/js/js_json_intro.asp) - w3schools

[JSON Parse](https://www.w3schools.com/js/js_json_parse.asp) - w3schools

[JSON Stringify](https://www.w3schools.com/js/js_json_stringify.asp) - w3schools

> Read through and look at examples for the entire JSON sections on [w3schools]() and [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON).
> See also the sec

#### Prototypes and inheritance

[A beginner's guide to JavaScript prototype](https://www.freecodecamp.org/news/a-beginners-guide-to-javascripts-prototype/) - Tyler McGinnis

[JavaScript Object Prototypes](https://www.w3schools.com/js/js_object_prototypes.asp) - w3schools

[JavaScript Prototype](https://www.javascripttutorial.net/javascript-prototype/) - JavaScript Tutorial

#### Node, Files, and JSON

[Reading and writing JSON files in Node.js: A complete tutorial](https://blog.logrocket.com/reading-writing-json-files-nodejs-complete-tutorial/) - Joseph Mawa, LogRocket Blog

[Reading and Writing JSON Files with Node.js](https://stackabuse.com/reading-and-writing-json-files-with-node-js/) - Scott Robinson, StackAbuse

[Read/Write JSON Files with Node.js](https://heynode.com/tutorial/readwrite-json-files-nodejs/) - hey(node)

[How to read and write JSON file using Node.js](https://www.geeksforgeeks.org/how-to-read-and-write-json-file-using-node-js/) - GeeksForGeeks

[How to work with Node.js and JSON file](https://www.geeksforgeeks.org/how-to-work-with-node-js-and-json-file/) - GeeksForGeeks

### Notes

#### Reading and writing files in Node

##### Write out to a file

We will start off with the same thing as previously to get data. 

```curl.js
import minimist from 'minimist';
import fetch from 'node-fetch';
// Get command-line arguments
const args = minimist(process.argv.slice(2));
// Put args onto STDOUT
//console.log(args)
// Get a URL
const response = await fetch(args._[0]+'?'+args.d)
// Store the response JSON data in an object
const data = await response.json();
// Echo back the data to SDOUT
//console.log(data);
```

But instead of logging it onto STDOUT, we are going to write it to a file with the `fs` builtin. 

```curl.js
// Load fs built-in
import fs from 'fs';
// Stringify data
let dataString = JSON.stringify(data)
// Write the data to a file
fs.writeFileSync("./current_weather.json", dataString)
```

If we want to add this as an option, let's say `-o`, what do we need to do?

We need to wrap the last line in a conditional and replace the filename with a call to `args.o`, which will send the data to whatever we specify on the command line.

```curl.js
if (args.o) {
fs.writeFileSync(args.o, dataString)
}
```

We have to stringify the data to write it to a file or Node will throw us an error, because we are only allow to write text strings to plaintext files.

#### Reading data from file

Okay, so what if we have some data in a file?

Let's read that in using Node.

And then let's write a script to read a file.

```read_data.js
// Load built-in fs module using CommonJS syntax
const fs = require('fs');
// Read our JSON file into a variable
let currentJSON = fs.readFileSync("./current_weather.json"); 
// Put the data back out onto STDOUT
console.log(currentJSON);
```

What's happening here? 

We are reading a JavaScript object into a variable from a file and then echoing that back onto STDOUT but it is not going to make any sense because all we are seeing is the memory buffer.
We need to convert the object BACK into a string in order to make it make sense for us.

```read_data.js
// Load built-in fs module using CommonJS syntax
const fs = require("fs");
// Read our JSON file into a variable
let currentJSON = fs.readFileSync("./current_weather.json"); 
// Convert data back to string
let currentString = JSON.parse(currentJSON);
// Put the stringified data back out onto STDOUT
console.log(currentString);
```
