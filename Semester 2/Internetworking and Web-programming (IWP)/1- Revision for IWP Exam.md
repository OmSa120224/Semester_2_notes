Started: 2024-05-29 - Cramping 5 ECTC ($\approx$ 150 hours) in 9 days 🥲.
Exam: 2024-06-07
______
# Lecture 1 -  Course introduction and introduction web-programming
## Course Intro

Course's Goal
![[IWP course goal.png]]


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
