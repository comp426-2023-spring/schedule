# 15 - HTML & CSS

## Week of 2023-03-21

### Agenda

1. Basic HTML document structure
2. Web server handling of HTML and related files
3. Elements & attributes
4. Responsive structure underlying design
5. Basic CSS principles
6. Page style with CSS

### Notes and recommended tutorials

I recommend working through the entire list of HTML tutorials available at w3Schools on lefthand menu on the main page.

It is extremely easy. THey are very short. And by the end you will have a relatively complete basic understanding of how HTML works.

This lesson will focus a bit more on things like syntax, structure, and relationships so that we can understand HTML programmatically.

#### 1. Basic HTML document structure

HyperText Markup Language (HTML) is a markup langauge used to make plaintext into dynamic interfaces.
A markup language is not a programming language, per say, but it has programmatic features.
It's best understood as a set of directives for how text or other visual features in an interface should be presented. 

I am using the term "interface" here in the broadest possible sense, per usual. 

A book, a paper codex with boards on the front and the back and a bunch of bound paper pages with glyphs inscribed upon them, is an interface.

A webpage, viewed in a web browser, is an interface. 

The former is not dynamic.

Once it is printed, it does not change readily.
Markup on an interface like a book is not dynamic and only appears as scribbling on printed pages. 

The latter, however, is very dynamic.

The text can change and be updated dynamically. 
The shape and style and colors of the text can be updated dynamically. 
Markup in an interface like a web page provides directives about how the interface should be update and under what circumstances.

Start with the basics: [a simple HTML document](https://www.w3schools.com/htmL/html_intro.asp).

Pay attention to syntax and style: [this will make your life easier](https://www.w3schools.com/html/html5_syntax.asp).

Know where the visible and invisible pieces go: [head elements](https://www.w3schools.com/htmL/html_head.asp).

#### 2. Web server handling of HTML and related files

Your webserver will serve all of the files in a directory to a client.

The client actually assembles the document by drawing information from the links referencing other files on the server.

Make sure you understand how this works: [file paths](https://www.w3schools.com/htmL/html_filepaths.asp).

#### 3. Elements & attributes

Everything between two carets `<>` is called a tag or an element: [HTML elements](https://www.w3schools.com/htmL/html_elements.asp).

They can be nested, but you must ALWAYS close your tags.

Elements have extra information in the open tag provided by attributes: [HTML attributes](https://www.w3schools.com/htmL/html_attributes.asp).

These can provide extra information about an element, like its [class](https://www.w3schools.com/htmL/html_classes.asp) or [ID](https://www.w3schools.com/htmL/html_id.asp), OR they can provide a directive, like the [URL where a link should point](https://www.w3schools.com/htmL/html_links.asp).

Some of these have names that make it very clear what they are, while others are not quite as clear: [know your semantic elements](https://www.w3schools.com/htmL/html5_semantic_elements.asp).

Most of the w3schools tutorials are about how to use different elements, like [headings](https://www.w3schools.com/htmL/html_headings.asp), [paragraphs](https://www.w3schools.com/htmL/paragraphs.asp), and [lists](https://www.w3schools.com/htmL/html_lists.asp).

For full list of HTML elements/tags, see the [reference list](https://www.w3schools.com/tags/).

#### 4. Responsive structure underlying design

Responsive design is crucial now.
There is no excuse to not be using responsive design when creating web documents.

It is important because it allows us to design for mobile devices first, meaning that your web documents will always be readable and usable no matter what device they are presented on. 
This is important from an accessibility and usability perspective.

Read this [Hands-On Guide to Mobile-First Design](https://www.uxpin.com/studio/blog/a-hands-on-guide-to-mobile-first-design/) from [Studio by UXPin](https://www.uxpin.com/studio/).

To get started with responsive design structure, start here: [basic responsive design principles and methods](https://www.w3schools.com/htmL/html_responsive.asp).

This will help you to better understand general HTML layout and how it can be structured to facilitate responsive design: [layout elements and techniques](https://www.w3schools.com/htmL/html_layout.asp)

#### 5. Basic CSS principles

Review at least the basic w3schools CSS tutorials: https://www.w3schools.com/css/default.asp.

Cascading Style Sheet (CSS) language is used to [style HTML elements](https://www.w3schools.com/css/css_intro.asp)
