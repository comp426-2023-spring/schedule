# 17 Document Object Model (DOM)

## 2023-03-31

### Agenda

- What is the DOM?
- How does it work?
- How do we use it to manipulate markup and other components of a web interface?

### Useful resources

[HTML DOM](https://www.w3schools.com/js/js_htmldom.asp) - w3schools

[Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) - MDN WebDocs

#### Tutorials

[How the JavaScript DOM Works – A Practical Tutorial](freecodecamp.org/news/the-javascript-dom-a-practical-tutorial/) - Ophy Boamah, FreeCodeCamp

### Notes

We'll start off with some very simple HTML and work through manipulating the elements through the corresponding nodes in the DOM. 

```index.html
<html>
    <head>
        <title>Document Object Model</title>
    </head>
    <body>
        <p>What is the DOM?</p>
    </body>
</html>
```

If we look at these elements as a hierarchy of nodes, then we can represent them something like this:

- html
    - head
        - title
            - text: "Document Object Model"
    - body
        - p
            - text: "What is the DOM?"

And we will go from there.

