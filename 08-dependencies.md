# 07 Dependencies

## 2023-02-09

### Agenda

- Dependency management
- `require()` vs. `import`
- Linking local dependencies
- Creating internal dependencies

# Slides



### Useful resources

#### Dependency management

[Understanding dependency management with Node Modules](https://levelup.gitconnected.com/understanding-dependency-management-with-node-modules-1c47bcdee98b) - Jason Lai

[Node.js dependency management](https://developer.ibm.com/tutorials/learn-nodejs-manage-packages-in-your-project/) - J Steven Perry

[Node Dependency Management](https://hexquote.com/nodejs-dependency-management/) - Jawad Hasan Shani

[Node Dependency Management (Part2)](https://hexquote.com/node-dependency-management-part2/) - Jawad Hasan Shani

[Quality code: Node.js design patterns and dependency management](https://sprkl.dev/quality-code-node-js-design-patterns-and-dependency-management/) - Luciano Mammino

[It depends. The art of dependency management in Javascript](https://blog.softwaremill.com/it-depends-the-art-of-dependency-management-in-javascript-f1f9c3cde3f7) - Michał Ostruszk

[Tips for Managing npm Dependencies](https://blog.shiftleft.io/tips-for-managing-npm-dependencies-599fc978f9c2) - Katie Horne

#### `require()` vs. `import`

[Difference between Node.js require and ES6 import and export](https://www.codingninjas.com/codestudio/library/difference-between-node-js-require-and-es6-import-and-export) - 

[Import vs Require in Node.js](https://masteringjs.io/tutorials/node/import-vs-require) - 
Pradipta Choudhury

[Compare require() vs import() in ](https://javascript.plainenglish.io/require-vs-import-in-js-82a7a47671f) - Sumeet Bhalla

[Require vs Import](https://www.educba.com/require-vs-import/) - Priya Pedamkar

[Using Node.js require vs. ES6 import/export](https://stackoverflow.com/questions/31354559/using-node-js-require-vs-es6-import-export) - StackOverflow

[Require vs. Import in JavaScript](https://stackdiary.com/require-vs-import-in-javascript/#:~:text=require%20is%20a%20function%20used,and%20ready%20to%20be%20used.) - Alex Ivanovs

[Difference between node.js require and ES6 import and export](https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/) - GeeksForGeeks

#### Node documentation

[Modules: CommonJS modules](https://nodejs.org/docs/latest-v18.x/api/modules.html)

[Modules: ECMAScript modules](https://nodejs.org/docs/latest-v18.x/api/esm.html)

[Modules: node:module API](https://nodejs.org/docs/latest-v18.x/api/module.html)

> Particularly important here is `module.createRequire()`, which gives you the ability to [construct the require function](https://nodejs.org/docs/latest-v18.x/api/module.html#modulecreaterequirefilename) when you working with an ES module.

[Modules: Packages](https://nodejs.org/docs/latest-v18.x/api/packages.html)

#### Local dependencies

[npm-link](https://docs.npmjs.com/cli/v8/commands/npm-link)

[Understanding npm-link](https://medium.com/dailyjs/how-to-use-npm-link-7375b6219557) - Franziska Hinkelmann

[How to NPM Link to a local version of your dependency](https://medium.com/@AidThompsin/how-to-npm-link-to-a-local-version-of-your-dependency-84e82126667a0 - Aid Thompsin

[https://www.viget.com/articles/how-to-use-local-unpublished-node-packages-as-project-dependencies/](https://www.viget.com/articles/how-to-use-local-unpublished-node-packages-as-project-dependencies/) - Henry Bley-Vroman

[4 reasons to avoid using `npm link`](https://hirok.io/posts/avoid-npm-link) - Hiroki Osame

### Notes

