Started: 2024-05-29 - Cramping 5 ECTC ($\approx$ 150 hours) in 9 days 🥲.
Exam: 2024-06-07
______
# Lecture 1 -  Course introduction and introduction web-programming
## Course Intro

Course's Goal
![[IWP course goal.png]]

pr
5-layers model of the Internet
![[IWP 5 layers of the internet.png]]


Topic need to know for the exam
![[IWP topics to know for the exam.png]]
___
## Intro to web technologies 

### Client-Server model
In the context of web development, a client and a server have distinct roles and characteristics:
![[IWP client server model.png]]

**Client**:
- A client is typically a web browser such as Google Chrome or Mozilla Firefox1. 
- The client makes requests to a server, usually for resources like web pages, images, or data.
- Clients do not share any of their resources.
- The client is responsible for rendering the received data, which could be HTML, CSS, JavaScript files, images, etc.
- The client can also send data to the server, such as form inputs.
- Clients are prone to viruses, Trojans, and worms if present in the Server or uploaded into the Server.

**Server:**
- A server is a software application or hardware device that stores, processes, and serves web content to users over the internet.
- The server responds to the client’s requests by delivering the requested content.
- Servers operate on the Hypertext Transfer Protocol (HTTP), which is the foundation of data communication on the World Wide Web.
- Servers handle user requests, often concurrently.
- They direct URL matching and rewriting.
- Servers process and serve dynamic content.
- They compress content for optimized data usage and speed.
- Servers enable browser caching for your static content.
- Servers are prone to Denial of Service (DOS) attacks.

In the **client-server model**, when the client computer sends a request for data to the server through the internet, the server accepts the requested process and delivers the data packets requested back to the client. This model is widely used in applications such as email, World Wide Web, etc.

## The Front-End Triangle
The “Front End Triangle” refers to the three core technologies used in front-end web development: HTML, CSS, and JavaScript. Here’s a brief overview of each:

**HTML (HyperText Markup Language):**
- HTML is the structure of a web page.
- It provides the basic layout and structure for the web page, such as headers, paragraphs, links, images, etc.
- HTML elements are represented by tags.

**CSS (Cascading Style Sheets):**
- CSS is the presentation layer of a web page.
- It is used for styling and layout of web pages.
- CSS can be used to create various shapes and designs.

**JavaScript (JS):**
- JavaScript is the behaviour layer of a web page.
- It is a programming language that makes web pages interactive.
- JavaScript can manipulate both HTML and CSS.

Together, these three technologies form the basis of front-end web development. HTML provides the structure, CSS adds style, and JavaScript adds interactivity. This is often referred to as the “Front End Triangle” in web development.

## Back-end(Server-Side) technologies
![[IWP back-end Arche.png]]

## JS 
### The use if JS in front-end 
- Interactivity 
	- Validation of user input and meaningful error messages
	- Dynamic rendering of web page, depending on user’s choices 
	- Control of GUI elements: sliders, menus, pop-ups,… 
	- Application functionality
- Server communication 
	- Dynamic loading of data from server, filtered view
	- Updating of web page without explicit “reload” 
	- Minimize server communication: some data processing can be done locally without using network and server. 
- Program functions 
	- Lighter calculations and program parts, which the client “conveniently” can perform locally 
	- Functions it should take care of, if server is “down”

### Use of JS in back-end
- The same as other server scripting languages
	- Receiving HTTP requests from clients 
	- Decoding of parameters and forms 
	- Validation of received data 
	- Application functions and calculation (which is included in the answer to clients) 
	- Lookups in and updating of databases or files 
	- Generation of dynamic HTML pages 
- Implementation of WEB APIs 
- Serving of files 
- Handling of data and functions, which should be shared between different clients.

## Difference between website and web application
![[IWP Website-vs-App-Table.png.webp]]

A web application, also referred to as a web app, is a computer program with functionality and interactive elements. You use regular web technologies to build it but it also stores data and manipulates it according to a user's needs.

A website is a collection of publicly accessible pages containing either documents, images, audio, text, or other files that users can access through the internet. Websites can consist of a single page or many pages. In order for a user to access a website, they will need a URL which they enter in the search bar of their web browser.

___
____
# Lecture 2 - JavaScript Functions and Objects

- **Three methods got defining a function in JS**
    - **Function declarations**
        - Most commonly used
        - The keyword “function”
        - Can be called before they are declared (“hoisted”)
    - **Function expressions**
        - Creates a function value
        - Used in expressions or sentences where you need a function value
        - Can be bound to a name via “let” or “const” like all other values
    - **Arrow function expressions**
        - Compact alternative to regular function expressions
        - Typically used to create a “small” function that is passed as a parameter
        - Related to “lambda expressions”
        - Has certain differences and limitations in connection with methods and objects

```three methods to define a function in JS
// funktions kald/applikation/anvendelse/invokation
//bmi er synlig her, da dens funktionserklæring ”hoistes”
let b=bmi(1.80,90); //27.78


// funktions erklæring
function bmi(h,w){
return w/(h*h);
}


//funktions udtryk (anonymt),
let bmi2= function(h,w){
return w/(h*h);
};
b=bmi2(1.80,100); //30.86


//funktions udtryk (navngivet)
bmi2= function calcBMI(h,w){return w/(h*h);};
b=bmi2(1.80,110); //33.95
let bmix=bmi2;
b=bmix(1.80,120); //37.03

 
//pile‐funktioner
const bmi3 = (h,w) =>{ return w/(h*h)};
b=bmi3(1.80,130); //40.12


//hvis kun 1 parameter: parentes i parameter liste unødvendig
//hvis kun 1 statement: fjern {}, og ”return” er underforstået
const incr = a => a+1;
b=incr(5);//6
```


## JS Object literals

Objects are used to encapsulate related data and the functions that work on them data together in a logical unit

**The following list is for the code block below**
• A collection of "properties"
• Map from key (unique name) to value ("key-value")
• propertyName: propertyValue
• An object literal is created using { }
• Period notation to access the key's value
• Keys can be strings with spaces, but Don't! *)
• An object can be bound to a name via const and let.
• The name "points to" the object.
• A property can be dynamically created (and removed!)

```
let student1={
name:"Gynter",
studentID:12345678,
"Yndlings Sang": "Højt på træets grønne"
}

console.log(student1.name);
console.log(student1["Yndlings Sang"]);

student1.age=42;
console.log(student1);



{
name: 'Gynter',
studentID: 12345678,
‘Yndlings Sang': 'Højt på træets grønne top',
age: 42
}

```



### Object Serialization

Serialization is a term for turn structured data into a "flat" (bit or character strength).
• Save object to files
• Send over network
```
let serializedHans=JSON.stringify(hans);
let hans2=JSON.parse(serializedHans);
console.log("Serialized object: "+serializedHans);
console.log(hans2);
```

JSON JavaScript Object Notation,
• Standardized data exchange format for JS objects
• Only "data" properties are included, **NOT**  functions
• As readable text
```
Serialized object: {"name":"Hans","grades":[{"kursus":"IWP","karakter":‐ 3},{"kursus":"SLIAL","karakter":4},{"kursus":"Imperativ Programmering:","karakter":7}]}
```

JSON object with the methods
• stringify() //object to string
• parse() // string to object



## JS Arrays
Arrays are Objects where the properties/keys are numbers!
methods: push, pop, map, reduce.
```
let diceRoll=[1,6,6,2,3,4,6];
let dice2=new Array(1,6,6,2,3,4,6);
//prepared to hold 10000 elems.
let dice3=new Array(10000);


let sl=dice2.slice(2, 4); //[ 6, 2 ]
console.log(sl); //[6,2]


sl.push(1); //[6,2,1]
sl.push(2); //[6,2,1,2]
sl.push(3); //[6,2,1,2,3]
console.log(sl.pop()); //3
console.log(sl); //[6,2,1,2]

console.log("Index på første 6er: "+ diceRoll.indexOf(6));//

```


### JS Arrays: Iterables
```
let diceRoll=[1,6,6,2,3,4,6];
for(let d of diceRoll){
console.log("Dice " +d);
}

let diceSum=0;
for(let d of diceRoll){
diceSum+=d;
}
console.log(diceSum); //28

function printDiceHeading(dice){
console.log(`<h3> Dice ${dice}</h3>\n`)
}
diceRoll.forEach(printDiceHeading)
```

JS Arrays (sparse)

The `forEach` method skips holes.
```
let sparse=[];
sparse[7]="Hejsa";
sparse[42]="med";
sparse[100]="dig!";
console.log(sparse.length);//101!

console.log(sparse[10]); //undefined
sparse.forEach(s=> console.log(`heading ${s}`)); //prints all values, incl holes.

for(let [i,d] of sparse.entries()){ console.log("index "+i+" value "+d);
}
//iterates over non‐holes. 
let s=""; diceRoll.forEach(d=>s+=`heading ${d}\n`);
console.log(s
```


JavaScript Objects: Prototypes
JavaScript: Prototypes
**Extending** object by adding properties
**Overriding** methods by replacing the m. specialist version


A little general about objects


Brug OO og inheritance sparsommeligt:


```
class Student{
constructor(name) {this.name=name}
sayHello (name){ console.log(`Hello ${name}, my name is ${this.name}!`);} 
think() { return this.name+ " is thinking hard ...;};
}

class SoftwareStudent extends Student { 
	code() { return this.think()+ " and is coding the pants off";}
}

let b1 = new Student("Brian1");
let b2 = new SoftwareStudent("Brian2");
console.log(b2.code());
console.log(b1.think());
console.log(b1.code()); //Students don't generally code; so trying code() on a student fails.
}
```

___
____
# Lecture 3 - Wb-sites with HTML, Forms, HTTP basics, CSS

## URLs
URL stands for: Uniform Resource Locators

it is a A reference to an available resource aka web address

Indicates where the resource is located and how it is accessed
![[IWP lecture 3 URL parts.png]]

**Protocol (more correctly "scheme")**: Specifies the service (HTTP, FTP, file, mailto, tel, IRC,...) the browser must access (often corresponding to an application-level protocol

The domain: DNS (Domain Name System) name or IP address, as well as port number "130.225.63.3:8080"
	• Default: 443 (HTTPS) 80 (HTTP)

**Path name**: Name of resource within the domain in question: sometimes translated to a file name.

**Search string**: a series of "key-value" pairs that the server program can use to find the desired (part of) the resource: serves as a parameter list for scripts

Fragment: a way of asking for a portion of a document.

### Hypertext & Markup-sprog
**Definition**: Hypertext involves collecting text information and linking it through references (hyperlinks), allowing the information to be read in a user-defined sequence.

**Definition**: "**Markup**" refers to the markings, additions, and annotations that add extra information about a (text) document.

**Definition** **Markup Language**: The computer language (syntax and semantics) used for markup.


### Key Categories of HTML Elements
HTML has between 110-120 different elements 
1. **Metadata Content**: Elements that go inside the `<head>` section to provide information about the document.
    - Examples: `<title>`, `<meta>`, `<link>`, `<style>`, `<base>`
      
2. **Sectioning Content**: Elements that define the structure and outline of a document.
    - Examples: `<header>`, `<footer>`, `<section>`, `<article>`, `<nav>`, `<aside>`
      
3. **Content Grouping**: Elements that group other content together.
    - Examples: `<div>`, `<p>`, `<hr>`, `<ol>`, `<ul>`, `<li>`, `<dl>`, `<dt>`, `<dd>`, `<figure>`, `<figcaption>`
      
4. **Text Content**: Elements that define the text content and its structure.
    - Examples: `<span>`, `<a>`, `<strong>`, `<em>`, `<abbr>`, `<blockquote>`, `<cite>`, `<q>`, `<code>`, `<pre>`, `<b>`, `<i>`
      
5. **Inline Text Semantics**: Elements that provide meaning to the enclosed text.
    - Examples: `<b>`, `<i>`, `<u>`, `<mark>`, `<small>`, `<del>`, `<ins>`, `<sub>`, `<sup>`
      
6. **Forms and Input**: Elements used for creating forms and capturing user input.
    - Examples: `<form>`, `<input>`, `<textarea>`, `<button>`, `<select>`, `<option>`, `<label>`, `<fieldset>`, `<legend>`
      
7. **Interactive Elements**: Elements that enable user interaction.
    - Examples: `<details>`, `<summary>`, `<dialog>`
      
8. **Embedded Content**: Elements used to embed other content like images, audio, video, etc.
    - Examples: `<img>`, `<audio>`, `<video>`, `<iframe>`, `<embed>`, `<object>`, `<param>`, `<source>`, `<track>`
      
9. **Tabular Data**: Elements used to create and manage tables.
    - Examples: `<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>`
      
10. **Scripting**: Elements related to scripting and programmatic interaction.
    - Examples: `<script>`, `<noscript>`, `<canvas>`
      
11. **Web Components**: Elements for creating reusable components.
    - Examples: `<slot>`, `<template>`

An HTML element is the basic building block of an HTML document. It consists of several key parts:

1. Elements Name : The start of the element, enclosed in angle brackets $< >$. It usually contains the element's name and can include attributes. Also called tag
2. **Content**: The information or other HTML elements nested inside the element. Some elements are empty and don't have content.
3. **Attributes (optional)**: Provide additional information about an element and are included in the opening tag. Attributes have a name and value pair. Attributes are in the opening tag.
Example: **Anchor** element which makes a hyperlink
![[IWP anchor elements example.png]]

### HTML Syntax: Nesting 
Nesting must be balanced(start and end)
![[IWP nesting example 1.png]]
nesting can be shown as a tre
![[nesting can be shown as a tre.png]]

### class and  id attributes 
All html elements can have an id, which must be unique in the document.

All html elements can be grouped in classes.
makes it possible to change the CSS for all of the elements in the same class.

### HTML header and body
HTML Table

### HTML elements 
https://html.spec.whatwg.org/


There are online validators that can check for syntax and individual
semantic errors in HTML documents and CSS
 https://validator.w3.org/ 

inputs exampel
![[example of input in html.png]]

Validation of input on client vs server side 
![[Validation of input on client vs server side.png]]



## Basic HTTP
### HTTP
1. **Protocol**: HTTP is the foundational protocol used to transfer data between a web browser and a server.
2. **Port**: By default, HTTP uses port 80.
3. **Security**: HTTP is not secure. Data transferred using HTTP is sent in plain text, making it vulnerable to interception and attacks such as man-in-the-middle (MitM) attacks.
4. **Use Cases**: HTTP is suitable for non-sensitive data transfers where security is not a concern, such as accessing public web pages where no sensitive information is exchanged.

### HTTPS
1. **Protocol**: HTTPS is the secure version of HTTP. It uses SSL/TLS (Secure Sockets Layer/Transport Layer Security) to encrypt data transferred between a web browser and a server.
2. **Port**: By default, HTTPS uses port 443.
3. **Security**: HTTPS is secure. Data transferred using HTTPS is encrypted, making it much harder for attackers to intercept and read the data. HTTPS ensures data integrity, confidentiality, and authenticity.
4. **Use Cases**: HTTPS is essential for any website that handles sensitive information, such as login pages, online banking, e-commerce sites, and any form submission that includes personal or sensitive data.

### Key Differences
1. **Encryption**:
    - **HTTP**: Data is transferred as plain text.
    - **HTTPS**: Data is encrypted using SSL/TLS, protecting it from eavesdropping and tampering.
2. **Security**:
    - **HTTP**: Vulnerable to attacks such as MitM, where attackers can intercept and manipulate data.
    - **HTTPS**: Provides protection against such attacks, ensuring data integrity and privacy.
3. **Performance**:
    - **HTTP**: Generally faster due to the absence of encryption overhead.
    - **HTTPS**: Slightly slower due to the encryption and decryption process, though modern optimizations have minimized this difference.
4. **SEO and Browser Indicators**:
    - **HTTP**: Most modern browsers mark HTTP sites as "Not Secure", which can deter users.
    - **HTTPS**: Browsers display a padlock icon to indicate a secure connection, and search engines like Google give preference to HTTPS sites in search rankings.


## Simple  HTTP Example Scenario:


## HTTP/1.1 methods (aka ”verbs”)
- **GET**: Retrieve data without affecting the state of the resource.
- **POST**: Send data to create a new resource and potentially change the state.
- **PUT**: Update an existing resource or create it if it doesn't exist, replacing the resource completely.
- **DELETE**: Remove a resource from the server.

other examples
- **HEAD**: Retrieve headers.
- **PATCH**: Partially update data.
- **CONNECT**: Establish a tunnel.
- **OPTIONS**: Describe communication options.
- **TRACE**: Loop-back test for debugging.

## Content-Type header
### Key Points About `Content-Type` Header

1. **Purpose**: Specifies the media type of the resource or the data being sent to the server.
2. **Usage in Requests**: When a client sends data to a server (e.g., via POST or PUT), the `Content-Type` header tells the server the format of the data.
3. **Usage in Responses**: When a server responds to a client, the `Content-Type` header tells the client the format of the returned data.
4. Content-type must be given correctly: MIME type Multi-purpose Internet Mail Extensions
![[IWP file ends and MIME.png]]

## HTTP Respond codes

![[IWP respond codes basics.png]]
The link in the sheet: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

#### HTTP and FORMS: GET
### HTTP and FORMS: **POST**

### Cascading Style Sheets (CSS)

CSS rules
![[IWP CSS rules.png]]

CSS properties examples: include lots of examples



### Selectors in CSS (important)
![[IWP selectors in CSS.png]]
the link: https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#in_this_module

A CSS selector is the first part of a CSS Rule. It is a pattern of elements and other terms that tell the browser which HTML elements should be selected to have the CSS property values inside the rule applied to them


#### Cascade rules: How styles interact
![[IWP CSS cascading.png]]

____
____
# Lecture 4 -Web-apps: Multi-page vs. Single Page


## HTTP Crash Course
https://www.youtube.com/watch?v=iYM2zFP3Zn0
### what is HTTP
![[what is http.png]]
### HTTP is stateless
![[HTTP crash course http stateles.png]]
### What is HTTPS
![[what is https.png|400]]
SSL stand for **secure sockets layer**
TLS stand for **transport layer security**
### HTTP methods 
the main four are(there are more)
![[HTTP methods.png|400]]

### HTTP header fields 
![[http header example.png]]
Common HTTP fields, but there is more
![[HTTP header fields.png]]

### General Headers
These headers apply to both request and response messages.
1. **Request URL**: The URL to which the HTTP request is being made. or the URL one is requesting
2. **Request Method**: The HTTP method used for the request, such as GET, POST, PUT, DELETE, etc.
3. **Status Code** (important): The HTTP status code returned by the server, indicating the result of the request (e.g., 200 for OK, 404 for Not Found).
4. **Remote Address**: The IP address of the server handling the request.
5. **Referrer Policy**: The policy that governs how much referrer information should be included with requests made by the user.

### Response Headers
These headers are included in the HTTP response sent from the server to the client.
1. **Server**: Information about the software being used by the server to handle the request. (e.g., **Apache**, **NGINX**)
2. **Set-Cookie**: Used to send cookies from the server to the client, which can then be stored and sent back with subsequent requests.
3. **Content-Type**: The media type of the resource being sent (e.g., `text/html`,`text/css` `application/json`).
4. **Content-Length**: The size of the response body in bytes.
5. **Date**: The date and time at which the message was sent.

### Request Headers
These headers are included in the HTTP request sent from the client to the server.
1. **Cookies**: Data stored on the client side that is sent to the server with each request, often used for session management and tracking.
2. **Accept-xxx**: Specifies the media types (like `Accept`, `Accept-Language`, `Accept-Encoding`) that are acceptable for the response.
3. **Content-Type**: The media type of the body of the request (used when sending data to the server, e.g., in a POST request).
4. **Content-Length**: The size of the request body in bytes.
5. **Authorization**: Contains the credentials for authenticating the client with the server.
6. **User-Agent**: Information about the client software initiating the request (e.g., browser type and version).
7. **Referrer**: The URL of the previous web page from which a link to the currently requested page was followed.

### HTTP Status Codes
![[http status codes.png|400]]
most common status codes 
![[most common status codes.png|400]]

### HTTP/2
![[HTTP version 2.png|400]]
Http 1.1 vs 2
![[http 1.1 vs 2 time line.png]]



______
____
# Lecture 5 - Client side scripting: Browser as runtime environment

**API**  stands for **API Application Programming Interface**: and is a collection of features that provide access to functionality in external program module / service


#### API documentation:
Important 
• DOM
• Fetch
https://developer.mozilla.org/en-US/docs/Web/API


## Document Object Model
The Document Object Model (DOM) is **a programming interface for web documents**. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.
## Tree structure for HTML
![[Tree streuc of elements.png]]
### Tree structure for HTML: "The HTML Element Tree"
Each HTML element has the following properties
• **children**: an array like object with the children
• **firstElementChild, lastElementChild**: designates first and last child
• **nextElementSibling, previousElementSibling**: hooks siblings together in a double-linked list
• **parentNode** parent element


### Tree structure for HTML: The "element tree": traversal
![[The element tree traversal.png]]


### Tree structure for HTML: the "NODE tree"
Everything in an HTML document is a node object:
• The document itself is a node
• All HTML elements are "element nodes"
• Text within HTML elements "text nodes"
• Comments are “comment nodes

![[Example-of-DOM-Node-Tree.png|650]]

### Tree structure for HTML: The "NODE tree": Traversal
the node contains the text too
![[node tree traversal.png]]

Browser maintains 2 trees
• The node tree
• The element tree: A la Node tree, where ONLY HTML elements are included
• USE THE ELEMENT TREE!
• "search" with: querySelector()

## HTML Element properties
Each HTML element has the following properties
• `textContent`: returns the text of the element and its descendants.
• `innerHTML`The HTML code for the "innards" of an element, and its successors.

```
document.body.textContent;
document.body.children[2].textContent ="and Cola";
document.body.children[2].innerHTML ="and <em> beer </em>"
```


> [!quote] Title
> Changes the html code for the last `<p>` element, and thus inserts subtree with the `<em>` element Writing to `.innerHTML` is usually a bad idea! Security hole! DON'T!!!


## Search for HTML nodes
The simple, classic
`let elem = document.getElementById(string);`
Searches the document for the (one) element whose id attribute=== string

The modern selector-based: easy, universal and flexible
• `document.querySelector(selectorString);`
• `document.querySelector(”#elem_id”):` same as `getElementById(”elem_id”)`
• `document.querySelectorAll(selectorString);`

## HTML Elements attributes in the DOM
The attributes of HTML elements are "mirrored" as properties in the DOM
![[html arti are dom prop.png]]

## Changing the DOM tree
Very flexible methods: append, prepend, after, before
• Creating new element: `createElement(elementName);`
• Deleting/replacing nodes: `replaceWith`, `remove`

![[createElement example.png]]


the line `const string = document.createElement("strong");`
is a JavaScript statement that creates a new HTML element. Here’s a breakdown of what it does:
1. **`const string`**: This declares a constant variable named `string`. The `const` keyword means that once this variable is assigned a value, it cannot be reassigned to a different value.
2. **`document.createElement("strong")`**: This is a method call that creates a new HTML element. Specifically, it creates a `<strong>` element. The `createElement` method is a function of the `document` object, which represents the entire HTML document.
```
const strongElement = document.createElement("strong");
strongElement.textContent = "This text is bold and important.";
document.body.appendChild(strongElement);
```


### append, prepend, before, and after.
1. **`append`**:
- **Usage**: `parentNode.append(...nodes or strings)`
- **Description**: Adds nodes or strings to the end of the list of children of the specified parent node. If a string is provided, it is inserted as a `Text` node.
- **Example**:
```
const parent = document.getElementById('parent');
const newElement = document.createElement('div');
newElement.textContent = 'Appended Element';
parent.append(newElement);
// Adds "Appended Element" to the end of the children of the parent element
```


2. **`prepend`**:
- **Usage**: `parentNode.prepend(...nodes or strings)`
- **Description**: Adds nodes or strings to the beginning of the list of children of the specified parent node. If a string is provided, it is inserted as a `Text` node.
- **Example**:
```
const parent = document.getElementById('parent');
const newElement = document.createElement('div');
newElement.textContent = 'Prepended Element';
parent.prepend(newElement);
// Adds "Prepended Element" to the beginning of the children of the parent element
```

3. **`before`**:
- **Usage**: `referenceNode.before(...nodes or strings)`
- **Description**: Inserts nodes or strings immediately before the reference node. If a string is provided, it is inserted as a `Text` node.
- **Example**:
```
const reference = document.getElementById('reference');
const newElement = document.createElement('div');
newElement.textContent = 'Before Element';
reference.before(newElement);
// Adds "Before Element" immediately before the reference element
```

4. **`after`**:
- **Usage**: `referenceNode.after(...nodes or strings)`
- **Description**: Inserts nodes or strings immediately after the reference node. If a string is provided, it is inserted as a `Text` node.
- **Example**:
```
const reference = document.getElementById('reference');
const newElement = document.createElement('div');
newElement.textContent = 'After Element';
reference.after(newElement);
// Adds "After Element" immediately after the reference element

```


## Events

### Call-back **functions**
callback = a function that is passed as an argument  to another function.  used to handle asynchronous operations: 
1. Reading a file 
2. Network requests 
3. Interacting with databases 
 "Hey, when you're done, call this next."


### Events
Browser generates an event when something "interesting" happens
• User input, mouse event
• The HTML document, or elements therein

JavaScript can subscribe to these events and execute a function when the event occurs
• Event handling function / "event-handler-function" / "call-back-function"

Create interactivity and dynamics on an HTML page;
everts types and examples
![[events example in web dev.png]]


### Event concepts
- Event type: Ex a click
- Event-target: The object which is exposed to the event, e.g. a specific HTML "button"
- Event handling function: a registered function, which is called when ending occurs
- Event object"): information about the incident
	- Passed as argument to event-handler function
	- includes "event-target", timestamp
	- For mouse events: $x,y$ position
- The registration mechanism: how an event trades are registered
- Propagation of the event: ("event propagation") how the event is captured and propagated in an HTML document with nested elements
![[event terms example.png|500]]

`addEventListener` Method allows multiple event handlers to be attached to the same event type without overwriting existing ones. It provides more flexibility and is generally preferred for adding event listeners.


### Default event handling
The browser has a number of standard event handlers:
• Clicking on a hyperlink: causes the browser to load the new web page
• Submit on form: the browser submits the form as specified in the form action and method.
• Click on an html element: usually nothing.
You can prevent the browser from performing the default action by
insert "`preventDefault()`" in your event handler.


### DOM API: EVENT Bubbling and capturing
There can be multiple handlers registered at different levels in the DOM the tree:

- An event is first handled by the handlers at the deepest nesting level
	- The event.target element
- Then “bubbles” up to handlers at parent levels (ancestors) 
	- The `event.currentTarget` element
- 3 phases in DOM
	1. Capturing: the event goes down towards the target.
	2. The target phase (target): the event has reached the target
	3. The bubbling phase: event is handled from target to ancestor (at superordinate levels)
- There are functions to handle events in these 3 phases and stop the propagation (in advanced GUIs, not critical for IWP)
![[the deepest nested elements.png]]

### HTML DOM Object-Orientation (advanced)
![[HTML DOM Object-Orientation (advanced).png]]
- Node types in DOM are represented as "classes" that "inherit" from each other
	- (in JavaScript: prototype chain)
	- EventTarget: Objects that can receive and handle DOM events
	- Node: Node in the DOM tree, adds properties applicable to nodes (e.g. childNodes)
	- Element: An element in the tree (basis for HTML elements) e.g. traversal properties (children)
	- HTML Element: Adds additional features for HTML elements
	- HTML Input element: Adds distinctive properties applicable to input elements (e.g. value)
- HTML Element thus has all the properties of Node, plus more
- An HTML Input Element is a special HTML Element
- All HTML Elements are like this `EventListeners`

## Loading JavaScript

### Loading JavaScript in the client
**Embedded JavaScript method:**
• the code is placed within an HTML `<script>` element.
• For simpler code for the document.
```
<script>
console.log("Hello IWP");
</script>
```

**External JavaScript method:**
• Usually recommended
• the code is specified as an external file in the HTML script element.
`<script src="arrays.js"></script>`
• Smaller HTML documents, sharing the script from several pages
• Typically contains definitions of complex functions and data, and entire libraries
`<script type="module"src="arrays.js"></script>`
• Placed in the HTML body (usually at the bottom, since the page is
recorded and DOM is ready)
• type=”module” attribute declares that it is an EC6 module:
import and export statements can be used
• Can also be linked in the header (typically if it is a general
library) 
	• Set any defer attribute

**inline JavaScript method:**
• code is placed directly within certain HTML attributes. Typical
for event handling functions for the element.
• There are better methods (`addEventListener`)
```
<a href="JavaScript:alert('hej');">info</a>
<input type="button" value="Send"
onclick="alert('Hej!');" >
```


### Loading HTML/JavaScript
#### loading phase
1. The HTML document is loaded, parsed/interpreted
	• Browser builds the structure of the page as a family tree of HTML objects
	• Downloading of external resources (CSS/Scripts/imgs) is started (separate HTTP calls)
2. When the browser encounters a `<script>` element, the script is executed
	• With less special cases: defer, async, or module scripts
	• Typically, a lot of functions and properties are defined.
3. Multiple scripts are executed in the ***order*** in which they are declared
	• With less special cases: defer, async, or EC6 module scripts
4. Remaining resources, e.g. images are retrieved, interpreted and displayed
5. The page has been downloaded, recorded: the status "load".
#### Event phase
• The browser listens for "events" from the user and system, and calls JavaScript functions for event handling (event-handlers)

### JavaScript code
Distributed as source code!
• Since the interpreter works directly with the source text.
• Anyone can read, inspect/debug, copy the code, output variables during runtime, e.g. using the browser's "developer mode"!
• Can be "obfuscated", which makes it difficult for people to find meaning of the code. Still does not hide sensitive information.
• Can be "minimized" so that it takes up less space (faster to load)

Code and information that must be kept secret from users,
• should not be sent to clients at all, but kept on the server side
• or sent and remain encrypted
• sensitive information (passwords, API-keys) which can be misused if they are read out, may not sent to the client: kept on the server side.


## **A little about security**
Code injection attack
Via user input to smuggle in code, as an attacker wishes fulfilled
• Well-known examples
	• SQL code injection
	• XSS: cross site scripting
• User input
• must be validated and sanitized (special characters must be escaped or stripped)
• Also all input from the web on the server side!!!

Code injection 1: via `document.write`
![[example of code injection.png]]

Code injection attack 2: via innerHTML
Code injection attack 3: via innerHTML


**Code injection attack**
• Hackers are always looking for loopholes!
• Cunning!
• Not just a JavaScript phenomenon
• Gaps on the client side
• ==ALL INPUT MUST BE VALIDATED, SANITIZED AND PROCESSED CAREFULLY==
• Holes on the server side:
• ==ALL INPUT FROM THE NETWORK MUST BE VALIDATED, SANITIZED AND PROCESSED CAREFULLY==

## Asynchronous program execution


The event loop
JS sequentially executes one handler function at a time and runs it to "end"
• Both node.js and browsers run this way.

Asynchronous execution: longer-lasting operations are broken up into 2 parts: Initiation and termination
• FX: ordering a timer; running the handler
• FX: registration of a "click" trader; running the handler when clicked
• FX: Send HTTP request; running handlers to handle the response.
• In the intervening period, other events take place!
• Program is divided into many handling functions (each of which runs continuously to the end)


Loading web resource from browser
• Downloading from the web is a time-consuming activity, processed
usually asynchronously!
1. Browser initiates loading; sending request
2. Listens for and processes events as normal
3. When the response arrives, it is processed

Otherwise, the page will "hang" and not feel interactive
• Also applies to long processing times from event handlers
`knapElem.addEventListener("click", (event) => { while(1); });`

### FETCH API
Fetch is a promise-based API for retrieving web resources introduced in "modern" JS
• Often the client loads JavaScript objects from the server side of the application
• Serialized as a text string in JSON format.
• Alternative in complex apps: "Call-back hell"
• ==Make asynchronous code "look" like synchronous code as a coherent sequence of actions==

•`let promise = fetch(url, [options])`
• `promise.then(f`): Executes the function `f` when the result is clear.
• For example, loading a JSON document from the server
```
fetch("scores.json")
	.then(response=> {return response.json()})
	.then(data=>{console.log(data);})
	.catch(reportError)
```

• Fetch uses GET by default, but can take an additional option argument for setup of method (e.g. POST), header, possibly body.

### JavaScript Promises
A promise is an object that is a placeholder for a future value (result
of an asynchronous action)
• For example, wait for the response to HTTP requests
• Goal: to simplify the structure and clarity of asynchronous programs
![[promeses ex.png]]
### Promises .THEN
`p.then(success callback, fail callback)`
• Registers 2 call-back functions that are executed when the lift is redeemed or rejected
• Waiting for the promise to be settled
• Returns a new promise object based on the return value of the `call-back` function
	• => then statements can be chained in sequence
• Normally, `.then` is used with only one argument: `success-callback`, and `fail-callback` is registered with `.catch():` `p.catch(fail‐callback)`
![[ex .then.png]]


#### Helper functions: jsonPost and jsonParse
![[Helper functions jsonPost and jsonParse.png]]
_________________
____________
# Lecture 6 - Asynchronies, Promises, Fetch 
Agenda
• Exceptions
• Timers, callbacks and events
• Promises
• Async/await
• Fetch


### Exceptions and Errors
Exceptions and Errors are synonyms in JavaScript
Meaning: an exceptional condition or error has occurred

**Terminology:**
An exception is thrown when the error or exceptional condition
happens
Catching an exception means handling the exception, to execute code e.g.: to recover from the exception.

### The big picture
- The `try` statement lets you test a block of code for errors
-  The `catch` statement lets you handle the error
- The `throw` statement lets you create custom errors
- The `finally` statement lets you execute code, after `try` and
`catch` blocks, regardless of the result

### Let us throw an exception
The exception can be a JavaScript String, a Number, a Boolean or an Object
```
throw "Too big";      // throw a text
throw 500;            // throw a number
```

- When the interpreter throws an error, it uses the Error class and its subclasses
- Properties: name (type of error) and message (holds the string passed to the constructor)
- JavaScript will actually create an Error object with two properties: name and message.
#### Example of and exception

![[example of throw and error.png]]


#### Execution flow
When an exception is thrown, JavaScript interpreter immediately
stops normal program execution and jumps to the nearest exception
handler
- It checks against the current block of code
- If no catch clause is found, next-highest enclosing block of code is considered
- If no catch clause is found in the function, exception is propagated up to the code that invoked the function
- If no catch clause is ever found, the exception is treated as an error and is  reported to the user
#### How to catch an exception
![[how to catch an expection.png]]
The finally code can throw an exception, which is propagated up; it can return to make the method return normally (no exception)

#### Error handling
Two philosophies for error handling
- One is the fail-silent approach where you ignore errors in the code
- The other is the fail-fast and unwind approach where errors stop the world and rewind
Better to stop code execution and let the user know, and possibly
inform the developer

#### Input Validation
Important use case for exceptions:
- Examine the input. If it is wrong, an exception is thrown
	- The exception is caught by the catch statement and a custom error message is displayed
Example of error handling 
![[Input validation.png]]
Another example of Error handling 
![[another example of the error hadling.png]]


### Asynchronous execution
- A program is doing something
- The current action has to wait for something before continuing
- The program wants to do something else while waiting

**Use cases:**
- JavaScript programs in a web browser are typically event-driven, and must wait for user input (e.g.: clicks)
- JavaScript-based servers wait for client requests to arrive over the network before they do anything

#### JavaScript mechanisms for asynchronous execution
- `Callbacks` are registered, and called when an event happens
- `Promises` are objects that represent not-yet available result of an asynchronous operation
- `async` and `await` provide a syntax for asynchronous programming to simplify Promise-based code

#### `Callbacks` for timers
- You can register a function
- It gets called when the Timer is fired (see previous lecture)
	`timerId = setTimeout(checkForUpdates, 60000);`
- The callback function is called one minute after `setTimeout` is executed
- `checkForUpdates` is called once at the correct time with no arguments, and nothing more
- Use instead `setInterval` to have periodic execution. You can later stop the periodic execution with `clearInterval(timerId)`. Don’t forget to save `timerId`
##### Example for timers
```
timerId = setTimeout(() => {
	console.log(“hello later”); // runs after 2 seconds }, 2000)
```

I can pass it more parameters:
```
const myFunction = (firstParam, secondParam) => {
	…
}
setTimeout(myFunction, 2000, firstParam, secondParam)
```

Similarly to the periodic execution, you can cancel the timer before the callback is called:
```
clearTimeout(timerId)
```

#### Callbacks for events
- Event-driven JavaScript programs register event handler functions for specified types of events (e.g.: ‘click’) in specified contexts (e.g.: `confirmUpdateDialog`’s button)
- The web browser invokes those functions whenever the specified events occur
```
let okay = document.querySelector('#confirmUpdateDialog button.okay’);
okay.addEventListener('click', applyUpdate);
```
- `applyUpdate` gets executed when the user clicks on the button of the dialog

#### Callbacks for file system events
Node.js processes files, networking, etc asynchronously
These operations can be time consuming, and are mediated by the operating system. The Node.js program can do something else in the meantime

#### Callbacks hell
- Imagine that you have to write callbacks for everything that can happen, and register and deregister them as needed
- Imagine also that a callback can define and register another callback, and so on and so forth
- Image having to read code from your colleagues where callbacks are indented on 5 different levels, since they are callbacks defined into callbacks that are defined into callbacks etc etc
- **Solution**: mechanisms to write synchronous-like code that is executed asynchronously


### Promises
A promise is a proxy for a value that will eventually become 
- You create it “around” a function (also known as `executor`) that takes two functions as parameters. One is executed if the executor completes correctly, one if there was a failure
- There is no way to synchronously get the value of a Promise; you can only ask the Promise to call a callback function when the value is ready
The Promise represents a computation that will eventually produce a
value or throw an exception
- Not good for repeated computation
#### Benefits of Promises
This solves two problems of “normal” callback-based programming:
- I don’t have callbacks inside callbacks inside callbacks (callbacks hell). Instead, I have Promise chains
- Error handling. It is impossible to just throw an exception, since there is no way for that exception to propagate back to the initiator of the asynchronous operation. Promises standardize how to handle errors


#### Using a Promise
Image that `getJSON(url)` returns a Promise, you can call its then
method to register two callbacks:
```
getJSON(url).then(
	jsonData => {
		// This is a callback function that will be asynchronously
		// invoked with the parsed JSON value when it becomes available.
	}, err => {
		// This code is executed when an exception is raised
	}
);
```

If the function in the first `then()` returns a promise, you can call the
`then()` method multiple times, each of the functions will be called on the promise returned by the previous function

#### Idiomatic best practices
- Call the `then()` method directly on the function invocation that returns a Promise, without assigning the Promise to an object
- Name the functions returning Promises with verbs
- Instead of passing a “reject” function, `catch()` the exception outside the `then()` invocation
	- As we discussed, the exception is propagated outward until it finds a `catch()`
![[Idiomatic best practices.png]]

#### More terminology: States
- A Promise can be *fulfilled* (correct computation of the final value, fist callback is called)
- A Promise can be *rejected* (failure with computing the value, Exception raised, second callback / `.catch()` is called)
-  Before that time, the Promise is *pending*. As soon as it is either *fulfilled* or *rejected*, the Promise is *settled*
- After the Promise is *settled*, it provide its *result* (either the computed value, or the Error) as soon as the *.then().catch()* is applied to the Promise
	- Maybe you are executing another function and you cannot yet execute the `.then().catch()`
	- Maybe you already did the `.then().catch()` and the callback will be called as soon as possible

#### Executing Promises sequentially
#### Chaining Promises
#### More complex example of chaining promises
- This example has one more step and error handling
- Each invocation of the `then()` method returns a new Promise, which is not fulfilled until the function passed to ITS `then()` is complete

![[example of then and promises.png]]

### More terminology: Fates
-  As soon as the callbacks registered using `then()` / `then().catch()` returns, the Promise is *resolved*. We can *resolve* a promise with another promise
- A Promise is *unresolved* if it is not *resolved*

**Relation States vs Fates:**
- Promise is not *fulfilled* if the callback returned a *pending* Promise (see chaining in next slide)
- A *fulfilled* Promise is *resolved*. A rejected Promise is *resolved*
- An *unresolved* Promise is *pending*
#### Resolved but not Settled?
As soon as the callbacks registered using `then() / then().catch() `returns, the Promise is *resolved*. We can *resolve* a promise with another promise. Can next then() method be called already?
lecture 6 slide 30


#### Definition of Resolved
- “resolved” Promise means: the Promise has become associated with, or “locked onto”, another Promise or a non-Promise value
- In some cases, we don’t know yet whether p will be fulfilled or rejected, but the callback has no control anymore over that
- Promise p is “resolved” in the sense that its fate now depends entirely on what happens to something else (the Promise it returned)

#### Error Handling
- We already discussed that the second callback is not usually provided
- Idiomatic approach similar to try/catch/finally:
- `getJSON("/api/user/profile").then(displayUserProfile).catch(handleProfileError).finally(cleanUp);`
- If `getJSON()` ends correctly, `then()` is invoked; if an Exception is raised (in `getJSON()` or in `then())`, the `catch()` is called. After `then()` end correctly or `catch()` ends, `finally()` is run
- One more example (`recoverFromStageTwoError()` returns a Promise):
```
startAsyncOperation()
	.then(doStageTwo)
	.catch(recoverFromStageTwoError)
	.then(doStageThree)
	.then(doStageFour)
	.catch(logStageThreeAndFourErrors);
```

#### Promises in Parallel
- You can create an array of Promises
`promises = urls.map(url => fetch(url).then(r => r.text()));`
- Then you can execute all of them in parallel:
``` 
Promise.all(promises)
	.then(bodies => { /* do something with the array of strings */ })
	.catch(e => console.error(e));
```

- The Promise returned by `Promise.all()` rejects as soon as any of the input Promises is rejected

#### Making Promises from a Promise
- Creating a Promise that encapsulate another Promise:
```
function getJSON(url) {
	return fetch(url).then(response => response.json());
}
```

- When the internal Promise `fulfills`, the promise returned by `getJSON()` fulfills as well
- Error handling:
	- Checking `response.ok` and the Content-Type header?
	- No, in this case it is easier: we just allow the `json()` method to reject the Promise it returned with a `SyntaxError` if the response body cannot be parsed as JSON
#### Making Promises from synchronous value
- Creating a Promise based on synchronous computation:
	- Compute your value
	- Use the static methods `Promise.resolve()` and `Promise.reject()`
```
Promise.resolve('Success').then(function(value) {
	console.log(value); // "Success"
});
```
- No real asynchronicity
- The Promise will be settled as soon as the computation is done
	- They will fulfill or reject **after** the current synchronous chunk of code has finished running
	- `console.log(value)` outputs “Success” after the current chunk of code ends
Example of making promises
![[Example of making promises.png]]
![[rest of example of making promises.png]]


## Async/await
- An `async` function is a function that implicitly returns a promise and that can, in its body, `await` other promises in a way that looks synchronous
- The `await` keyword takes a Promise and turns it back into a return value or a thrown exception (if you are into an `async` function)
- Here are three functions called x, y and z that return promises:
```
async function x() {return "one";}
let y = async function () {return "two";}
let z = async () => "three"
```
- Inside one of the promises, I can await:
```
async function do_it() {
	console.log("message is "+await y());
}
```
### Benefits of async/await
- Useful to forget about Promises and their complexity
- Given a Promise object p, the expression await p waits until p settles
	- If p fulfils, then the value of `await p` is the fulfilment value of p
	- If p is rejected, then the `await p` expression throws the rejection value of p
- When inside an `async` function there is an `await promise1`, your program stops until promise1 settles
	- Or actually, the function is put to sleep and JavaScript interpreter can do something else
	- Any code that uses `await` is itself *asynchronous*

### Idiomatic await
- It is placed before the invocation of a function that returns a Promise:
	- `let response = await fetch("/api/user/profile");`
	- `let profile = await response.json();`
- It is uncommon to bind the Promise to an identifier
- What if I am into a non-async function, or in the top level?
	- It is a Promise …
		- `getHighScore().then(displayHighScore).catch(console.error);`

### Awaiting multiple promises
![[Awaiting multiple promises.png]]

### Asynchronous loops
![[Asynchronous loops.png]]
#### For/await loops
It is Promise-based
- The asynchronous iterator produces a Promise
- The for/await loop waits for that Promise to fulfil
- The fulfilment value is assigned to the loop variable
- The body of the loop is executed
- Another Promise from the iterator is created and the loop repeats
Example of for/await loop 
![[for await loop example.png]]


## Performing HTTP/HTTPS requests
- Different methods can be used to perform HTTP requests
	- Old approach: `XMLHttpRequest.` Let’s forget about it
- Let us align on the “best” method we currently have: `fetch`
- `fetch()` defines a Promise-based API for making HTTP and HTTPS requests:
	- It accepts a URL and the kind of request as parameters
	- It returns a Promise that fulfils to the `response` (it was possible to contact the server) or it rejects if the HTTP connection could not be done
	- The `response` is a promise that resolves to a `body` (if the request went fine, e.g.: response code 200) containing the data
### Fetch basic examples
![[Fetch basic examples.png]]

### Fetch: better GET example
![[fetch get example.png]]
### Parsing the body
What can I do with request (= the result of a fulfilled `fetch` Promise)?
- Two most common way of parsing the result of the GET:
	- `response.json().then( … )` to get the result as a JSON object
	- `response.text().then( … )` to get the result as text
- Other useful methods:
- `response.formData().then(…)` to parse the result as a FormData object (“multipart/ form-data” format). Common to send data to a server, but not for the response
• Streaming! See next slide

#### Fetch Streaming API
- Do not get a Promise out of the response
	- If you access the data in any way (.json(), .text(), etc), you cannot re-access it
- The response has method `getReader()` to get a stream reader object:
![[Fetch Streaming API.png]]

### Fetch: a POST
![[fetch a post.png]]

### Security: CORS
- Web browsers generally disallow `fetch()` to servers different from the one the main HTML document comes from
	- Exceptions: images and scripts
- Cross-Origin Resource Sharing (CORS) aims to safe cross-origin requests
- The browser automatically adds an “`Origin`” header to the request
- The server has to explicitly answer with a “`Access-Control-Allow-Origin`” header, or the interaction is cancelled
	- Meaning, the Promise returned by `fetch()` is rejected
- The “`Origin`” header cannot be overridden via the headers property
### Aborting a Fetch request
- Need to create an `AbortController` PRIOR TO the `fetch()`
- Pass the `signal` property of the `AbortController` as the signal property in the options of the `fetch()`
- Call the `abort()` method of the controller to abort the request
- Let’s not get a Promise out of the response
	- If you access the data in any way (.json(), .text(), etc), you cannot re-access it
![[aborting a fetch req.png]]

___
____
# Lecture 9
Agenda
1. Structure of the Internet
2. Packet switching principle
3. Delay, Throughput, and Bottlenecks
4. Internet Protocol stack

## Structure of the Internet
What components does the network consist of?
How is it structured in networks of networks?

### What does the Internet consist of?
 **Billions of connected “computers” : (phones, laptops, PC, smartphones)**
• hosts = end systems
• Runs network applications

**Communication links (links)**
• fiber, copper, radio, satellite,…
• Transports data with a certain transmission rate:
• (Mega) bits-per-second (Mbps)

**packet switches**: device that forwards data packets in the network
• routers and Layer 2 switches


**Network**: collection of hosts, routers, links managed by an organization

## Simple model for the structure of the Internet
![[simple structure of the internet.png]]

**Network edge (edge):**
• hosts = than systems
• Clients and servers
• Servers, typically located in data centers

**Access network (access)**
• The outer link, connecting subscribers to their ISP
• Local network + connection to ISP
• Wired connections
• Wireless connections

**Network core (core):**
• Linked ISP routers
• Hierarchies
• Network of networks

• **Links**: the transmission medium between two
nodes (hosts/routers)


![[protocals illustrations.png]]

Protocols: Rules that govern the sending and receiving of messages
• Data content and format of messages
• What actions must be taken when receiving or sending messages?
• e.g., TCP, IP, HTTP, Skype, 802.11

Internet standards
• Described in "RFCs": Request for comments (http://www.rfc-editor.org/standards )
• by IETF: Internet Engineering Task Force (https://www.ietf.org/about/)


### Internet Structure: Network of Networks
Question: How are millions of ISP access networks connected?
Direct connections (links) between each ISP does not scale: O($N^2$ ) compounds.


One option: connect each access ISP to a global transit ISP?
Business agreement between customer and supplier ISPs
![[connect each access ISP to a global transit ISP.png]]

Better with more transit ISPs: Competition, decentralization, scaling, …
![[more transit ISPs.png]]

Some Transit ISPs want to connect with each other

IXP: Internet Exchange Point (IXP) I Physical and neutral location where different ISP networks meet and exchange traffic.
![[IXP exchange points.png]]

regional networks may arise that are desired to be connected to the global network
![[regional ISP.png]]


Major content providers (e.g., Google, Microsoft, Akamai) operate their own networks to deliver services and content closer to the end user

![[tiers of isp.png]]

A complex structure of inter-connected networks among
-  ISPs, Telecom providers, Content providers' networks (e.g., Google, Microsoft, Akamai)
- At the core: a small number of well-connected large networks, powered by Larger telecom and data communication companies
- Data centers concentrate many servers (“the cloud”), and content providers concentrate a lot traffic, often in own networks outside layer-1 or regional ISPs

## Packet-switching
What is packet switching?
Why and when is it smart?

**Packet switching**: sending host divides its data into smaller "data packets" 
• Forward packets from one router to the next on the path of links from source to destination
• Each packet is sent at the link's (full) transmission rate

**Store and forward**: the entire packet must be received by a router and stored in its memory before it can be forwarded on the next link

![[packet switching illus.png]]

**Delays**
• A packet that is *L-bits* long, sent at the rate *R bps*, takes *L/R* seconds to send
• Ex. Send delay: 1000 bits/1 Mbps = 1ms
• Ex. 2 hops to destination: Total delay: 2L/R (plus some more…)
• For example, on Ethernet the maximum packet size is L= 1522 bytes = 12176 bits


### Packet Switching: Packet queues and packet loss
If the arrival rate of a link exceeds its transmission rate over a short period of time:(if more packets arrive than what can be send, i queue is formed)
• Packets are queued and await transmission on link

![[packets queue.png]]
Queues occur when work arrives faster than that
can be treated

Packets are thrown out (dropped/lost) if the buffer runs out of space

Good for data traffic that comes in bursts: resource sharing (“statistical multiplexing”)
• If A and B transmit simultaneously, they must share the capacity of the output link (e.g. 1.5 Mbps)
• It is less likely that A and B both transmit with R at the same time for a long time
• If A sends "now" and B does not, A's traffic is forwarded at full 1.5 Mbps speed

• Without control: unrestrained degree of "constipation" (congestion)
• Alternative principle : circuit switching

### circuit switching
- Before data is sent, a path (circuit) is created between sender and receiver, like all data sent above
- Each circuit gets one pre-booked fixed transmission rate, e.g. 100 kbps
	- Available all the time, regardless of major or minor needs.
	- This makes it seem as if there is a dedicated "fixed" connection between transmitter and receiver

**Link capacity partitioning techniques**
• Frequency-Division Multiplexing
• Time-Division Multiplexing
![[FDM TDM.png]]

### Package clutch vs. circuit coupling
1 Gbps link, where each user uses 100 Mbps, but is only "active" 10% of the time
![[Package clutch vs. circuit coupling.png]]


### Two key functions of a router
Two key functions of a router are:
- Forwarding
- Routing
![[Two key functions of a router.png]]

## Delay, Throughput, Loss
How to determine latency through the network?
How is the possible transfer rate determined?

It takes some time to send (transmit) a bit on the medium (a)
• (too) simple example
• A logic 1 is coded as 3 volts for 1 μs
• A logical 0 is coded for 0 volts for 1 μs
• Provides transmission speed of 1 mega bits per second

There is a signal propagation time between transmitter and receiver (b)
• Depends on the medium and the distance between transmitter and receiver
• Barely the speed of light (approx. 2*108 m/s))
• Electrical signal in copper: approx. 70% of the speed of light
![[Delay in sedning data in a medim.png]]

### Sources of delay in a router
Time from when a packet has just been received in one node until it has just been received in the next
![[Time from when a packet has just been received in one node until it has just been received in the next.png]]
![[Sources of delay in a router.png]]

### Traffic Intensity
![[Traffic Intensity.png]]

### Throughput

throughput: speed (in bits/second) that can be transferred from
sender to receiver
• Instantaneous: speed at a given time
• Average: speed over a long period of time
• Pipeline analogy
![[Pipeline analogy.png]]

![[pipeline analogy 2.png]]

**bottleneck link**: The link on the end-to-end path that limits end-to-end throughput.

### Throughput: Internet Scenario
![[Throughput Internet Scenario.png]]

## TCP/IP protocol stack
What is a protocol stack?
What does a model for layering the internet protocols look like?
How are packets processed in the IP stack?

- “Protocol stack” collection of related protocols organized into layers
- TCP/IP Reference Model: A 5-layer model for the Internet protocols, which is extracted based on observations of a concrete network

![[internet layers.png]]
**Application layer**: Protocols that support the execution of network applications (mail, browser, file transport, ...)
• FTP, SMTP, HTTP, DN

**Transport layer**: Transfers data from a running program (process) on end-system A to counterpart on end-system B
• TCP, UDP

**Network layer**: routing and forwarding of packets from source to destination
• IP

**Link layer**: data transfer between direct neighbouring nodes in the network, i.e. connected by a single link.
• Ethernet, IEEE-802.11 (WiFi), PPP, SONET


**Physical layer**: bits “on the wire”


### TCP/IP Reference Model
- Narrow-waist/hourglass model: If we can transport IP on medium X, all transport and application protocols work too.
- “Lowest common denominator”
![[narrow waist model.png]]


### Abstract service description
- Each protocol instance "talks" virtually directly with its counterpart (peer)
- Each layer communicates only using the layer below
- Services offered by a lower layer can be accessed by upper layer via an interface
- At the bottom, messages are transferred on a physical medium
![[Abstract service description.png]]

## Services, Layer division, and encapsulation
Control flow goes down through the protocol layers
![[Control flow goes down through the protocol layers.png]]


### Segmentation and re-assembly
![[Segmentation and re-assembly.png]]
- Some layers and services support a maximum packet size
- Divide large packets into smaller parts ("protocol data unit"); re-assembled at recipient
- Division into smaller packages can in principle be done on all layers
 
### Why layering?
**Simplifies building complex systems:**
- Explicit structure allows single parts and their relationship to be identified and understood in smaller chunks
- Structure in simpler modules facilitates maintenance and updating of a system
	- Changing the implementation of a service can be done without changing the rest of the systems
**Disadvantages of layering?**
- Some functions can be difficult or expensive in terms of performance to implement
	- Stateful firewalls
	- NAT

**==IMPORTANT GENERAL COMPUTER LOGIC PRINCIPLE:==**
- Division of complex functionality into abstraction/virtualization layers each with well-defined functionality, which can be more or less tightly encapsulated

### OSI Reference Model
- A more "principled" model, standardized 7-layer model
	- Open Systems Interconnection Reference Model
	- International Organization for Standardization ("ISO 7498-2")
![[OSI Reference Model.png]]
1. Layer: Provides functions that users need
2. Layer: Conversion between different data representations: enables applications to interpret data based on their meaning, e.g. encryption, compression, machine specific conventions
3. Layer: Manages a dialogue: synchronization, checkpointing, re-creation of data exchange
4. Layer: Provides end-to-end delivery
5. Layer: Sending datagrams over multiple links
6. Layer: Sends frames with data
7. Layer: Sending bits coded as “signals”


### Criticism of OSI and TCP/IP
**OSI:**
Pros: Very influential model with clear concepts
Cons: The model, protocols and adoption hampered by politics and complexity

**TCP/IP:**
Pros: Very successful protocols that work well and are widely used
Cons: Weak model, which is subsequently derived from the current protocols

Domain names extractions
![[Domain names.png]]

DNS (Domain Name Server)
![[DNS domain name server.png]]
Internet Cache
![[Internet Cache.png]]
Internet Cookies
![[Internet Cookies.png]]



## Safety on the web???
- The web was originally made for a less closed group of users who trust each other
	- "security" is not built in, but added by new protocols and setting up restrictions on what is forwarded
- Packets can be "sniffed" (wireshark)
	- Broadcast media a la WiFi
	- Installed on router
- Packets can be "spoofed" (invent your own header)
- Denial of service attacks, DOS,…
- ...

Lecture 9
- Review: Have you understood basic concepts
	- Packet switching, delays, bottlenecks, protocol stack
- Exercises: Can you use them in new examples?
	- Concrete delay calculation
	- Bottlenecks
- Practical: Can use the network tools
- Traceroute, start Wireshark.

_______
___
# Lecture 10 - Application layer protocols
1. Application layer protocols and what are their needs for data- transportation
2. HTTP
	1. Structure of Notices
	2. Response time and persistent connections
	3. HTTP Caching
3. DNS
	1. Operation
	2. DNS caching
	3. DNS tools
4. (P2P)
	1. Bit torrent

## Application layer protocols
What are network applications and their communication needs?
How do application programs communicate with each other?
Which services does the transport layer in the TCP/IP model provide for applications?


## Network applications
**Programs such as:**
• Is carried out on (more different) than systems
• Communicates over the network
• Uses application-level protocols

**Examples**
• Web browser and web server,
• Discord
• Mail,
• Skype,
• YouTube, Zoom, Teams,
• FTP,
• BitTorrent application,
• GoogleDocs, , GitHub, Dropbox,
• CityProbe's data collection+dashboard


## **Application requirements for communication**
![[Application requirements for communication.png]]


## Application Layer Protocols
![[Application layer protocols.png]]
### A protocol defines:
- What **type of messages** are being exchanged?
	- e.g., request, response, ack,…
- Message **syntax**:
	- Which fields are in the message and how are they delimited?
	- That is defines parameters+structure
- Meaning of the message (semantics)
	- What does the information in the message mean?
- **Rules** for how messages must be processed and be answered

**Examples**:
• *Hypertext Transfer Protocol*, Simple Mail Transfer Protocol
• *Domain Name System Protocol*, WebSockets
• *Bit Torrent*, Network Time Protocol,
• …

**Open Protocols:**
• defined in RFCs
• allows interoperability
• e.g., HTTP, SMTP,
Proprietary protocols
• e.g., Skype

## Services from Internet transport protocols
### TCP (transmission control protocol) service:
- **reliable** transport of a sequence of bytes (“pipeline” / byte stream) between sender and receiver process
	- If the transmitter and receiver do not crash and the network does not fail permanently, data is delivered to the recipient correctly, without loss, in the order sent
- **flow control**: a fast transmitter does not overload the receiver
- **congestion control**: sends (down-)adjusts the send rate when the network is overloaded (traffic jam in a router)
- **Connection-oriented**: Must be established a connection between client and server process “handshake”

**DOES NOT GIVE**
- time/latency guarantees,
- no possibility of capacity reservation (minimum throughput),
- no security and encryption
	- (requires superstructure on the "transport layer security" application layer/ "Secure socket layer"

### UDP ("User datagram protocol") service:
- ” **best-effort** data transport
	- Datagrams
	- Connection less
	- ==Can be lost, duplicated, rearranged by the network (e.g. due to different route)==

**DOES NOT PROVIDE** 
- reliability, flow control, congestion control, timing, throughput guarantee, security, or connections
- SPM: What are we going to use it for? Why Does it exist?


## **Processes**
- The application layer communicates between processes on different hosts
- The application is executed in a "process" = a running program on one host
	- client process: process that initiates communication
	- server process: process which is waiting to be contacted
	- A given process can have both “roles”
- Processes can, for example, be displayed with "task manager" or "ps -aux"
- Processes on the same hosts can communicate by "inter-process communication"
	- `ls /usr/include | grep "stdio"`
- Between different hosts (host machines) using the transport layer

## Sockets
- Processes send/receive messages via a ("socket") **==socket==**,
- Link/door between application layer and transport layer
	-  Requires (at least) 2 sockets: one on each side
	- Created by the process when calling the "socket" programming interface
![[Sockets between aplication ana transport layer.png]]

### How to contact a Process?
For example, a server-process
- Must have a unique identification on the web
- Process is addressed using
	- Host's IP number e.g.: 130.225.63.3
	- A port number on the host e.g.: 80
	- CS web server can be contacted at: 130.225.63.3:80
	- Server process is expected to create a socket for the port that it uses to "listen" on
- More precisely: We contact the process on the specified host that listens on a "socket" which is bound to the specified port


Recognized services have permanently assigned, reserved ports
- Maintained by the Internet Assigned Numbers Authority (IANA)
- Port numbers 0-1023 are all reserved


## HTTP
What are HTTP control headers used for?
How are HTTP messages structured/formatted?
How is HTTP communication made more efficient?
How are connections to the server handled?
Why and how to "cache" HTTP documents?


### Simple HTTP Scenario: static html file
**HTTP: hypertext transfer protocol**
- application layer protocol for web traffic
- client/server model:
- client: program (typically browser)
	1. Client establishes TCP connection to server, typically port 80
	2. Sends a request (via HTTP GET) about a web page
	3. Awaiting response
	4. Parses response and records the page
	5. Runs possibly steps 1-4 again (in parallel) to retrieve required embedded resources (images, js scripts, style sheets)
- server:
1. Waiting
2. Receives HTTP request from client
3. Processes it and calculates answers (e.g. loads the file),
4. Sends an HTTP response (e.g. with file content) to the client

The server and the resource are indicated by a Uniform
Resource Identifier, usually URL

### HTTP Messages (syntax)
HTTP request
• Sent as text (human-readable)
• In protocol descriptions, the format is set up as a table with fields
HTTP request illustration
![[HTTP request and respone illus.png]]

HTTP request example
![[HTTP example illus.png]]


#### HTTP Messages: Response
similar to requests
HTTP response illustrantion
![[HTTP response illus.png]]

![[HTTP respone example.png]]

### HTTP Features
• Content negotiation (preferred formation)
==• Connection management==
• Cookies for session management
• Cross Origin Resource Sharing (CORS)
• Access control (Authentication)
==• Caching==
• Data Compression
• Redirection
• Portion reading (range requests)
https://developer.mozilla.org/en-US/docs/Web/HTTP


## HTTP
Connection management
How is HTTP client-server communication made more efficient?
How is TCP best used?


### HTTP Response Time
**RTT (definition): round-trip time**: the time it takes for the client to send a small packet to the server and receive the answer

**HTTP response time**
- An RTT to set up the TCP connection (handshake)
- An RTT for the HTTP request and the first few bytes of the HTTP response
- File transmission time
- 2RTT+ file transmission time

![[HTTP response time.png]]
**Simple browsers retrieve linked objects sequentially**
- If the procedure is repeated sequentially for each object it becomes **slow** to load a page
- In the example: 4* HTTP Response time
- 1\*HTTP Response time to retrieve the page /page.html
- + 3\*HTTP Response time for retrieving linked objects
- >8 RTT
http response time example
![[HTTP response time example.png]]

### HTTP Response time with parallel connections
Client can create several **"parallel" connections** to server

**HTTP response time:**
- 2RTT+ file transmission time + server overhead and possibly Capacity limitations downlink to client
- **Much faster for the client**
- **Demanding for the server**, as it must reserve buffer capacity for each connection (do this for many cliffs)
![[parallel responses.png]]
- In the example: >2* HTTP Response Time
- 1\*HTTP Response time to retrieve the page (/page.html)
- + 1\*HTTP Response time for retrieving linked objects
- +transmission time for 3 files
![[HTTP response time example.png]]

#### Solution: Persistent HTTP
**Persistent HTTP (default in HTTP/1.1):**
- Server keeps the connection open after sending response
- Subsequent HTTP requests and responses are sent on same open connection:
	- Saves overhead when establishing TCP connections
**HTTP Pipelining**
- Requests can be "pipelined": sent one after the other without waiting for answer "assembly line principle"
![[http alive connectionj.png]]

**HTTP response time with pipelining:**
- 2RTT+ file transmission time+server overhead and Possibly. capacity limitations downlink to client
- Much faster for the client
- Less demanding on the server, as it only has to maintain one connection per client, however the  client must close the connection as soon as it is finished.

**the example:**
• 1* HTTP Response Time (GET /page.html)
• 1\*RTT+3\*file transmission time
GET style.css
GET script.js
GET photo.jpg
![[HTTP response time example.png]]
- HTTP/2 takes this idea further

### HTTP/2

Goal: reduce the delay in multi-object HTTP requests

HTTP/2: \[RFC 7540, 2015\] increased server flexibility when sending
of web objects to client:
- methods, status codes, most header fields unchanged from HTTP 1.1
- The transmission order of requested objects is based on a priority specified by the client (not necessarily FCFS: First-Come-First-Serve)
- Server can send (push) objects to the client that it does not (yet) have requested
- Division of larger objects into "frames", scheduler frames in order to least HOL ("Head of Line") blocking
![[head of line blocking.png]]

### HTTP/2: reduction of HOL blocking
HTTP/2: object is divided into chunks (“frames”); sending frame
merged after they are ready at the server.
![[HOL reduction http2.png]]

### From HTTP/2 to HTTP/3

HTTP/2 over single TCP connection means
- Retransmission in case of packet loss gets transmission by all objects for stalling (TCP: orderly, reliable byte-streaming service)
	-  As in HTTP 1.1, browser gets incentive to open multiple parallel TCP connections two reduce stalling, thus increasing overall throughput
- No security over TCP connection
- HTTP/3: adds security, per object error and congestion control over UDP (QUIC)
- A little more when we get to the transport layer

## HTTP Caching
A "cache" is a local storage (repository) that stores copies of requested objects in order to provide quick access to it

Browser saves recently used objects/files on client
1. Browser first looks in the cache for the requested item object ("file") exists there
2. If yes, retrieve the object from there
3. If no, send request to web server
4. Cache the object and deliver the object

![[Cache illustration.png]]

- Only the server (and web app programmer) knows about the "mutability" of the object
	- Rarely change: CSS files, most images, icons, trademarks, static html files
	- Frequently changes: dynamic HTML based on DB lookups

## HTTP Cache control: Conditional query
![[Cache conditional query.png]]
**Max‐age:** indicates in seconds how long the object can be considered "fresh" and thus about the client must use the cached object
• Fresh: Time interval from when server generates answer + max‐age
• Typically calculated on the basis of Date or Last‐modified header in response
• Stale: expiry date exceeded

- If Stale: Client uses "Conditional Get" which checks with the server whether the object of the cache is up-to-date
	- The client stores the received time stamp together with the object, and sends this along
- Server sends one of 2 possible responses:
-  Object has not changed since \<timestamp>:
	- NO data, possibly new extended lifetime
	- The object has changed since \<timestamp>+data

### HTTP Cache control: Conditional query, **TAGS**
![[cache etag.png]]
ETAG: a string that acts as version number that the client can use to validate whether the content is an object it has is the "same" as the server's

Conditional Get: checks about the version of the cache matches the server's version.  The client also sends the receive version number

### HTTP Cache control
No‐cache: local content must always be validated at server first (still saves data if the object must be recycled)

No‐store: The object must not be cached; must be fetched again for each request.

Private vs. public. Private on only caches in the client's cache

Max‐age , If‐modified‐since

Link: https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching
Link: https://developer.mozilla.org/en-US/docs/Glossary/cacheable


### HTTP Proxies
A proxy is  ”man-in-the-middle”
Lecture 10 slide 37



## Domain Name System (DNS)
general info 


## DNS messages

## DNS Tools

## Peer-to-Peer Systems
Client-Server vs p2p
![[server vs p2p.png]]
Client-server sharing time
![[Client server download time.png]]
P2P sharing time
![[P2P sharing time.png]]

The tasks for lecture 10
• Review: Have you understood basic concepts
• Client and server "roles", cookies, DNS queries
• Exercises: Can you use them in new examples?
• Examining the HTTP header
• Time difference between different HTTP connection strategies
• HTTP cache (conditional get)
• P2P download times
• Practical: Can use the network tools
• Wireshark: intercept and examine the exchanged DNS messages

_________
___________
# Lecture 11 - The transport layer protocols and reliable communication

Understand tasks, services, and protocols on the transport layer
• TCP and UDP

How these tasks are solved 
• The link between the application layer and transport layer:
• "primitives" (operations)
• "sockets" and "demultiplexing"
• Establishing TCP connections

How can a Host A send a stream
of data to Host B loss-free.
• How to make reliable end-to-end communication?
• Detection of lost messages?
• Retransmission
• Using sequence numbers?
• (go-Back-N, Selective Repeat)
• "Sliding windows"
• Description of protocol as state machine, (illustration of scenarios via sequence diagrams)

## Transport layer protocols

### The transport layer in the TCP/IP model
![[tcp ip model.png]]

### A reliable transport protocol
How do you ensure that data can arrive with packet loss?
How is a protocol modelled and specified?
How is a protocol implemented?

How to determine "timeout" time?
• Too long: Unnecessary slow
• Too short: unnecessary retransmission of data and ACK
• Estimated from RTT
• Varies dynamically according to network load
• Find a good timeout value, but can never avoid too early / too slow timeout
## Pipelined protocols
How do we quickly transport a lot of data correctly to the recipient?
Can we avoid a stop&wait?
![[pipeline protocol.png]]


## Selective Repeat
Allow the sender to have max N packets in the "pipeline"
• GBN discards correct packets that arrive out-of-order
• In Selective Repeat:
• Receiver stores packets that arrive out-of-order in a buffer
• Recipient acknowledges individually for each package received
• Sender only retransmits the packets that lack a receipt
• Sender sets a timer for each individual packet it sends

Selective Repeat
![[selective repeat.png]]


## Establishing TCP connections
How does a client connect to a server?
How do they stop communication and bring down the connection again?


### TCP header
![[TCP header.png]]


### 3-way-handshake
![[3 way handshake.png]]


Controlled shutdown
![[Controlled shutdown.png]]

## Multiplexing/Demultiplexing
How are many compounds distinguished?
How to get data to/from the right socket?

• Process is addressed using the host's IP number + port number within a host
• Processes send/receive data via a socket, a link between the application and transport layers
• There are many processes on a host, thus many that the transport layer must serve
• A process can communicate with many others simultaneously (can thus have many sockets)
• How is data delivered to the right socket?
![[muti-demultip- plexing.png]]


### Demultiplexing
Host receives an IP datagram
• Each datagram has a source IP address, dest IP address
• Each datagram carries one transport layer segment
• Each transport-layer segment has one source and destination port
• Host user IP address and port numbers to forward data to it intended socket
![[TCP UDP segment format.png]]


#### Demultiplexing in UDP
Receiving socket identified by recipient IP and port (dest IP, dest port)
- Receiving UDP segment:
	- Checks to see if there exists an active socket on dest port
	- Forwards data to this
• NB! 2 UDP segments with same dest, but different src is delivered to the same socket
• NB! Source IP and port must known if the sender must could answer recipient
![[Demulti UDP.png]]

#### Demultiplexing in TCP
TCP socket is identified by 4-tuple ):
– source IP address
– source port number
– dest IP address
– dest port number
• demux: receiver uses all 4 values to forward to the intended recipient socket
• server process can have many simultaneous TCP connections (e.g., to each web client):
– Each socket is identified by its own 4-tuple
![[demulti in tcp.png]]

The tasks Lecture 11

• Review: Have you understood the basics concepts
• Demultiplexing,
• Retransmission Strategist: Go-N-Back, Selective retransmission,
• Exercises:
• Control of protocol state machine: alt-bit
• Sliding windows
• Practical: Can use the network tools
• Portscan with NMAP: which applications are listening on one given HOST?
______
______
## Lecture 12 TCP and Using the transport layer in programs: Socket programming

Agenda
3.5 connection-oriented transport: TCP
– segment structure
– reliable data transfer
– flow control
3.6 principles of congestion control
3.7 TCP congestion control


## Transmission Control Protocol:
- point-to-point:
	- one sender, one receiver
- full duplex data:
	- bi-directional data flow in same connection
	- MSS: maximum segment size
- reliable, in-order byte stream:
	- no “message boundaries”

- connection-oriented:
	- handshaking (exchange of control msgs) initializes sender, receiver state before data exchange
- pipelined:
	- TCP congestion and flow control set window size
* flow controlled:
	* sender will not overwhelm receiver

## TCP segment structure 

- ==Src/dst ports==
	- ==TCP and UDP have different namespaces==
- ==Seq/ack numbers to the byte==
Flags:
- CWR and ECE – explicit congestion notification
- URG and PSH – urgent data
- SYN and FIN seen in lecture 11
- ==ACK is 1 if the ACK number is valid==
- RST to kill the connection
- Header length – needed since “Options” has variable length
- Receive window: for flow control
- Internet checksum: 16-bit checksum for TCP header, payload, and some data from IP (routing layer)
- Urgent data pointer: used with the URG flag
- Options: for example to set the maximum size of the segments, or timestamp
![[TCP segment stuctrute.png]]



## TCP Sequence Numbers, ACKs


## TCP Retransmission Scenarios
![[TCP Retransmission Scenarios.png]]

### TCP ACK Generation
![[TCP ACK Generation.png]]


## TCP Flow Control
receiver controls sender, so sender won’t overflow receiver’s buffer by transmitting too much, too fast


## Principles of Congestion Control
informally: “too many sources sending too much data too fast for network to handle”

manifestations:
– lost packets (buffer overflow at routers)
– long delays (queueing in router buffers)

flow control vs congestion control
– buffers of the receiver vs network resources
– knowing the state of the receiving buffers vs estimating the state of the network

![[Causes Costs of Congestion Scenario.png]]

## TCP Congestion Control: Additive Increase Multiplicative Decrease



###  TCP Congestion Control: the sender
rate 
![[TCP Congestion Control  the sender.png]]


### TCP Throughput
average TCP
window size
average thruput
![[TCP Throughput.png]]


## The Socket
- Formed by the concatenation of a port value and an IP address
	- Unique throughout the Internet
- Used to define an API
	- Generic communication interface for writing programs that use TCP or UDP
- Stream sockets
	- All blocks of data sent between a pair of sockets are guaranteed for delivery and arrive in the order that they were sent
- Datagram sockets
	- Delivery is not guaranteed, nor is order necessarily preserved
- Raw sockets
	- Allow direct access to lower-layer protocols

### Defining a socket:
Two main things to do
- Addressing
	- Specifying a host and a service (IP + port)
	- It is a tuple (“www.cs.aau.dk”, 80)
- Data transport
	- Mainly TCP (SOCK_STREAM) or UDP (SOCK_DGRAM)


### Socket Programming with UDP
UDP: no “connection” between client & server
• no handshaking before sending data
• sender explicitly attaches IP destination address and port # to each
packet
• receiver extracts sender IP address and port# from received packet

UDP: transmitted data may be lost or received out-of-order Application viewpoint:
• UDP provides unreliable transfer of groups of bytes (“datagrams”)
between client and serve

### Client/Server Socket Interaction: UDP
![[ClientServer Socket Interaction UDP.png]]


### Socket Programming with TCP
![[Socket Programming with TCP.png]]

### Client/Server Socket Interaction: TCP
![[Client Server Socket Interaction TCP.png]]

### The Socket API
![[The Socket API.png]]


C Server  slide 41 lecture 12 
C Client
JavaScript Server
JavaScript Client
Windows programming slide 45 


### Issues:
![[Issues.png]]


#### Issues with the recv()


_________
_____
# Lecture 13 - Security in computer networks

Agenda
8.1 What is network security?
8.2 Principles of cryptography
8.4 Authentication
8.3 Message integrity
8.6 Securing TCP connections: SSL
8.7 Network layer security: IPsec

## What is Network Security?

![[network security triangle.png]]

**confidentiality**: only sender, intended receiver should “understand” message contents
	– sender encrypts message
	– receiver decrypts message
**authentication**: sender, receiver want to confirm identity of each other
**authorization**: each authenticated user must be able to do a set of tasks
**message integrity**: sender, receiver want to ensure message not altered (in transit, or afterwards) without detection 

**access and availability**: services must be accessible and available to users

STRIDE
![[STRIDE.png]]



### Toy SSL: A Simple Secure Channel
- handshake: Alice and Bob use their certificates, private keys to
authenticate each other and exchange shared secret
-  key derivation: Alice and Bob use shared secret to derive set of keys
- data transfer: data to be transferred is broken up into series of records
- connection closure: special messages to securely close connection
![[simple handshake ssl.png]]

### Toy: Key Derivation
![[values meaning key derivation.png]]


### Toy: Sequence Numbers 
![[Sequence Numbers.png]]

### Toy: Control Information
![[Control Information.png]]


### Toy SSL: Summary
![[Summary SSL.png]]

### SSL Cipher Suite
![[SSL Cipher Suite.png]]
### SSL Record Format
![[SSL Record Format.png]]


### Real SSL Connection
![[Real SSL Connection.png]]

____
____
# Extra

TCP vs UDP
![[TCP VS UPD.png]]


Multiplexing, 
![[Pasted image 20240606012025.png]]
de-multiplexing
![[Pasted image 20240606012053.png]]


![[STRIDE.png]]
authentication, and confidentiality against spoofing
itegrity against tampering
![[Pasted image 20240606013413.png]]

# Formulas

The transmission delay (also known as the transmission time) is the amount of time required to push all the packet's bits into the wire. It can be calculated using the formula:
$$Transmission\;\; delay = packet\;\; length / Rate = L/R$$


The propagation delay is the time it takes for a signal to travel from the sender to the receiver. It can be calculated using the formula:
$$
propagation\;\; delay= distance/propagation\;\; speed =d/s
$$
propagation speed  is usually the speed of light in vacuum

The total delay in a network link is the sum of the transmission delay and the propagation delay.
$$
Total\;\; delay= transmision\;\; delay + propagation\;\; delay

$$

 link utilizations is the actual transmission rate over the maximum transition rate.

 utilizations is also how much is being used of the total possible transmission rate



![[Pasted image 20240606145319.png]]
To determine the end-to-end throughput experienced by the clients for their downloads, we need to identify the bottleneck link for each path from the servers to the clients. The throughput of each path will be limited by the link with the smallest bandwidth in that path.

the answer is 4 as all of them are sharing the link R3 and it is the bottleneck for all of them.



Units
![[maxresdefault.jpg]]


Et streaming firma skal have uploadet et ny datasæt på 40 terabytes til en server, der er placeret tæt hos forbrugerne, men et stykke væk fra firmaet. Deres Internet forbindelse til serveren tillader en gennemsnitlig upload hastighed på 100 Mbps. Hvor lang tid tager det? Sammenlig tid og pris med at sende en fysisk pakke med et speditionsfirma med næste-dags levering. Antag firmaet køber en dedikeret forbindelse til serveren, med 10 gange højere kapacitet. Hvor lang tid tager det så? Hvad bliver den gennemsnitlige udnyttelsesgrad af denne, under antagelse af at et nyt datasæt uploades en gang om måneden, og den daglige trafik (email, web-surfing, etc) udgør 20 Mbps i gennemsnit. Overvej de praktiske konsekvenser i scenariet.

![[Pasted image 20240606150633.png]]




#### Lecture 10 e
An **authoritative DNS server** holds and provides definitive answers to DNS queries about domain names within its administrative control. Here's why:

1. **Authority**: The authoritative DNS server has the original source of DNS records for the domains it manages. This includes records such as A, CNAME, MX, and NS records, among others.
    
2. **Responsibility**: When a domain (e.g., enterprise.com) is registered, the authoritative DNS server is designated as responsible for providing DNS responses for that domain. This server is listed in the NS (Name Server) records at the parent domain level, such as in the TLD (Top-Level Domain) DNS servers.
    
3. **Accuracy**: Unlike caching DNS servers or recursive resolvers, which may provide temporarily stored data, the authoritative DNS server always provides the most current and accurate information about the domain's DNS records.
    
4. **Zone Management**: The authoritative DNS server is where administrators manage and update the DNS records for the domain. Any changes to the domain's DNS records must be made on this server.



## go back N protocol 
![[Pasted image 20240606205137.png]]


![[Pasted image 20240606210444.png]]

if frame two is not ACKed then frames 2,3 4 and 5 will be retrasmitted
![[Pasted image 20240606210636.png]]