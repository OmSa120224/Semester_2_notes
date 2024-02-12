Date: 09/02/2024
Literature: Chapter 6, 7, and 8
![[IWP Lecture 2 Reading.png]]______
____________
# Chapter 6 Objects

## 6.1 Introduction to Objects

> [!NOTE] Object
> An object is a composite value: it aggregates multiple values (primitive values or other objects) and allows you to store and retrieve those  values by name. An object is an unordered collection of properties, each of which has a name and a value.

Any value in JavaScript that is not a string, a number, a Symbol, or true, false, null, or undefined is an object.

objects are mutable and manipulated by reference rather than by value.

JavaScript uses the term own property to refer to non-inherited properties.

In addition to its name and value, each property has three property
attributes:
* The writable attribute specifies whether the value of the property can be set.
* The enumerable attribute specifies whether the property name is returned by a for/in loop.
* The configurable attribute specifies whether the property can be deleted and whether its attributes can be altered.


## 6.2 Creating Objects
Objects can be created with object literals, with the `new` keyword, and with the `Object.create() function`.

### 6.2.1 Object Literals
```
let empty = {}; // An object with no
properties
let point = { x: 0, y: 0 }; // Two numeric
properties
let p2 = { x: point.x, y: point.y+1 }; // More complex
values
let book = {
"main title": "JavaScript", // These property
names include spaces,
"sub-title": "The Definitive Guide", // and hyphens, so
use string literals.
for: "all audiences", // for is reserved,
but no quotes.
author: { // The value of this
property is
firstname: "David", // itself an object.
surname: "Flanagan"
	}
};
```

### 6.2.2 Creating Objects with new
```
let o = new Object(); // Create an empty object: same as {}.
let a = new Array(); // Create an empty array: same as [].
let d = new Date(); // Create a Date object representing
the current time
let r = new Map(); // Create a Map object for key/value
mapping
```
### 6.2.3 Prototypes
Almost every JavaScript object has a second JavaScript object associated with it. This second object is known as a prototype, and the first object inherits properties from the prototype.


### 6.2.4 Object.create()



## 6.3 Querying and Setting Properties
To obtain the value of a property, use the dot (.) or square bracket([]) operators.
```
let author = book.author; // Get the "author" property
of the book.
let name = author.surname; // Get the "surname" property
of the author.
let title = book["main title"]; // Get the "main title"
property of the book.
```


To create or set a property, use a dot or square brackets as you would to query the property, but put them on the lefthand side of an assignment expression.
```
book.edition = 7; // Create an "edition"
property of book.
book["main title"] = "ECMAScript"; // Change the "main
title" property.
```

### 6.3.1 Objects As Associative Arrays
The following two JavaScript expressions have the same value:
```
object.property
object["property"]
```


### 6.3.2 Inheritance
JavaScript objects have a set of “own properties,” and they also inherit a set of properties from their prototype object.
```
let o = {}; // o inherits object methods from
Object.prototype
o.x = 1; // and it now has an own property
x.
let p = Object.create(o); // p inherits properties from o and
Object.prototype
p.y = 2; // and has an own property y.
let q = Object.create(p); // q inherits properties from p, o,
and...
q.z = 3; // ...Object.prototype and has an
own property z.
let f = q.toString(); // toString is inherited from
Object.prototype
q.x + q.y // => 3; x and y are inherited from
o and p
```




_____
# Chapter 7. Arrays

> [!NOTE] Array
> An array is an ordered collection of values. Each value is called an element, and each element has a numeric position in the array, known as its index. JavaScript arrays are untyped: an array element may be of any type, and different elements of the same array may be of different types.

JavaScript arrays are dynamic: they grow or shrink as needed, and there is no need to declare a fixed size for the array when you create it or to reallocate it when the size changes.

## 7.1 Creating Arrays
There are several ways to create arrays.
* Array literals
* The ... spread operator on an inerrable object
* The Array() constructor
* The Array.of() and Array.from() factory methods


### 7.1.1 Array Literals
The simplest way to create an array is with an array literal, which is simply a comma-separated list of array elements within square brackets.
```
let empty = []; // An array with no elements
let primes = [2, 3, 5, 7, 11]; // An array with 5 numeric elements
let misc = [ 1.1, true, "a", ]; // 3 elements of various types + trailing comma
```

### 7.1.3 The Array() Constructor
Another way to create an array is with the Array() constructor.

You can invoke this constructor in three distinct ways:

* Call it with no arguments:
```
let a = new Array();
```
This method creates an empty array with no elements and is
equivalent to the array literal [].


* Call it with a single numeric argument, which specifies a
length:
```
let a = new Array(10);
```
This technique creates an array with the specified length.


* Explicitly specify two or more array elements or a single nonnumeric element for the array:
```
let a = new Array(5, 4, 3, 2, 1, "testing, testing");
```
In this form, the constructor arguments become the elements of the new array.


## 7.2 Reading and Writing Array Elements
You access an element of an array using the [] operator.
```
let a = ["world"]; // Start with a one-element array
let value = a[0]; // Read element 0
a[1] = 3.14; // Write element 1
let i = 2;
a[i] = 3; // Write element 2
a[i + 1] = "hello"; // Write element 3
a[a[i]] = a[0]; // Read elements 0 and 2, write
element 3
```



## 7.5 Adding and Deleting Array Elements
the simplest way to add elements to an array: just assign values to new indexes:
```
let a = []; // Start with an empty array.
a[0] = "zero"; // And add elements to it.
a[1] = "one";
```


You can delete array elements with the delete operator, just as you can delete object properties:
```
let a = [1,2,3];
delete a[2]; // a now has no element at index 2
2 in a // => false: no array index 2 is defined
a.length // => 3: delete does not affect array length
```

## 7.8 Array Methods
* Each of the subsections that follows covers a group of related array methods:
* Iterator methods loop over the elements of an array, typically invoking a function that you specify on each of those elements.
* Stack and queue methods add and remove array elements to and from the beginning and the end of an array.
* Subarray methods are for extracting, deleting, inserting, filling, and copying contiguous regions of a larger array.
* Searching and sorting methods are for locating elements within an array and for sorting the elements of an array

___
# Chapter 8. Functions

> [!NOTE] Functions
> A function is a block of JavaScript code that is defined once but may be executed, or invoked, any number of times.

If a function is assigned to a property of an object, it is known as a method of that object

Since functions are objects, you can set properties on them and even invoke methods on them.

## 8.1 Defining Functions



### 8.1.1 Function Declarations
Function declarations consist of the function keyword, followed by these components:

* An identifier that names the function. The name is a required part of function declarations: it is used as the name of a variable, and the newly defined function object is assigned to the variable.
* A pair of parentheses around a comma-separated list of zero or more identifiers. These identifiers are the parameter names for the function, and they behave like local variables within the body of the function.
* A pair of curly braces with zero or more JavaScript statements inside. These statements are the body of the function: they are executed whenever the function is invoked.



### 8.1.2 Function Expressions
Function expressions look a lot like function declarations, but they appear within the context of a larger expression or statement, and the name is optional.
```
// This function expression defines a function that squares its argument.
// Note that we assign it to a variable
const square = function(x) { return x*x; };
// Function expressions can include names, which is useful for recursion.
const f = function fact(x) { if (x <= 1) return 1; else return x*fact(x-1); };
// Function expressions can also be used as arguments to other functions:
[3,2,1].sort(function(a,b) { return a-b; });
// Function expressions are sometimes defined and immediately invoked:
let tensquared = (function(x) {return x*x;}(10));
```

### 8.1.3 Arrow Functions
you can define functions using a particularly compact syntax
known as “arrow functions.” This syntax is reminiscent of
mathematical notation and uses an => “arrow” to separate the function parameters from the function body.
```
const sum = (x, y) => { return x + y; };
```


## 8.2 Invoking Functions
The JavaScript code that makes up the body of a function is not executed when the function is defined, but rather when it is invoked. JavaScript functions can be invoked in five ways:
* As functions
* As methods
* As constructors
* Indirectly through their call() and apply() methods
* Implicitly, via JavaScript language features that do not appear like normal function invocations





### 8.2.2 Method Invocation
method is nothing more than a JavaScript function that is stored in a property of an object. If you have a function f and an object o, you can define a method named m of o with the following line:
```
o.m = f;
```
Having defined the method m() of the object o, invoke it like this:
```
o.m();
```
Or, if m() expects two arguments, you might invoke it like this:
```
o.m(x, y);
```


## 8.4 Functions as Values
The most important features of functions are that they can be defined and invoked. Function definition and invocation are syntactic features of JavaScript and of most other programming languages. In JavaScript, however, functions are not only syntax but also values, which means they can be assigned to variables, stored in the properties of objects or the elements of arrays, passed as arguments to functions, and so on.

