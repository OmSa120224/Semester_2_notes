Date: Friday 02/02/2024
Literature: JavaScript The Definitive Guide 7th Edition
![[Reading for Lecture 1 IWP.png]]
______
# Chapter 1. Introduction to JavaScript
JavaScript is a high-level, dynamic, interpreted programming language that is well-suited to object-oriented and functional programming styles.




_____
# Chapter 3. Types, Values, and Variables

## 3.1 Overview and Definitions
JavaScript types can be divided inro two categories: *Primitive types* and *Object types*. 

JavaScript’s primitive types include numbers, strings of
text (known as strings), and Boolean truth values (known as booleans).

Any JavaScript value that is not a number, a string, a boolean, a symbol, null or undefined is an object. 

> [!def] Definition: An object
> An object (that is, a member of the type object) is a collection of *properties* where each property has a name and a value (either s primitive or another object).
## 3.2 Numbers

The JavaScript number format allows you to exactly represent all integers between -9,007,199,254,740,992 ($-2^{53}$ ) and
9,007,199,254,740,992 ($2^{53}$), inclusive.

When a number appears directly in a JavaScript program, it is called a *numeric literal*

### 3.2.1 Integer Literals
In addition to base-10 JS recognizes hexadecimals (base-16) values, and they are *literals* that begins with `0x`, then followed by hexadecimals digits. 

In addition one could also express integers in binary(base-2) or octal (base-8) using prefix `0b` and `0o` or ( or `0B` and `0O`).

### 3.2.2 Floating-Point Literals
Floating-point literals may also be represented using exponential notation: a real number followed by the letter e (or E), followed by an optional plus or minus sign, followed by an integer exponent.
```
Syntax:
[digits][.digits][(E|e)[(+|-)]digits]

Example:
3.14
2345.6789
.333333333333333333
6.02e23 // 6.02 × 10²³
1.4738223E-32 // 1.4738223 × 10⁻³²
```

SEPARATORS IN NUMERIC LITERALS
You can use underscores within numeric literals to break long literals up into chunks that are easier to
read:
```
let billion = 1_000_000_000; // Underscore as a thousands separator.
let bytes = 0x89_AB_CD_EF; // As a bytes separator.
let bits = 0b0001_1101_0111; // As a nibble separator.
let fraction = 0.123_456_789; // Works in the fractional part, too.
```

### 3.2.3 Arithmetic in JavaScript
When the result of a numeric operation is larger than the largest representable number (overflow), the result is
a special infinity value, `Infinity`, or negative infinity for negative numbers.

The infinite values behave as you would expect: adding, subtracting, multiplying, or dividing them by anything results in an infinite value (possibly with the sign reversed).

Underflow occurs when the result of a numeric operation is closer to zero than the smallest representable number. In this case, JavaScript returns 0. Or "negative zero" for negative numbers.


* Division by zero returns infinity or negative infinity
* Zero divided by zero returns not a number (NaN)
* infinity divided by infinity also retunes NaN
* sqrt of a negative number
* arithmetic operates with non numeric operands

### 3.2.4 Binary Floating-Point and Rounding Errors
Approximation issue related to using binary floating point.
```
let x = .3 - .2; // thirty cents minus 20 cents
let y = .2 - .1; // twenty cents minus 10 cents
x === y // => false: the two values are not the
same!
x === .1 // => false: .3-.2 is not equal to .1
y === .1 // => true: .2-.1 is equal to .1
```


## 3.3 Text
The JavaScript type for representing text is the string.
JavaScript’s strings (and its arrays) use zero-based indexing: the first 16-bit value is at position 0, the second at
position 1, and so on.

### 3.3.1 String Literals
Strings in JS are enclosed in  (' or " or \`).  
```
"" // The empty string: it has zero characters
'testing'
"3.14"
'name="myform"'
"Wouldn't you prefer O'Reilly's book?"
"τ is the ratio of a circle's circumference to its radius"
`"She said 'hi'", he said.`
```


```
// A string representing 2 lines written on one line:
'two\nlines'
// A one-line string written on 3 lines:
"one\
long\
line"
// A two-line string written on two lines:
`the newline character at the end of this line
is included literally in this string`
```

### 3.3.2 Escape Sequences in String Literals
The backslash character (\\) has a special purpose in JavaScript strings. Combined with the character that follows it, it represents a character that is not otherwise representable within the string.
![[JavaScript escape sequences.png]]

### 3.3.3 Working with Strings
Working with strings and strings manipulation table page 92.

Remember that strings are immutable in JavaScript. Methods like replace() and toUpperCase() return new strings: they do not modify the string on which they are invoked.


## 3.7 The Global Object
vey important, but don't get it.


## 3.8 Immutable Primitive Values and Mutable Object References

There is a fundamental difference in JavaScript between primitive values (undefined, null, booleans, numbers, and strings) and objects (including arrays and functions). Primitives are immutable: there is no way to change (or “mutate”) a primitive value.


Objects are different than primitives, they are mutable. Objects are not compared by value: two distinct objects are not equal even if they have the same properties and values.
```
let o = { x: 1 }; // Start with an object
o.x = 2; // Mutate it by changing the value of a
property
o.y = 3; // Mutate it again by adding a new
property
let a = [1,2,3]; // Arrays are also mutable
a[0] = 0; // Change the value of an array element
a[3] = 4; // Add a new array element
```

And two distinct arrays are not equal even if they have the same elements in the same order:
```
let o = {x: 1}, p = {x: 1}; // Two objects with the same
properties
o === p // => false: distinct objects
are never equal
let a = [], b = []; // Two distinct, empty arrays
a === b // => false: distinct arrays are never equal
```

Objects are sometimes called reference types to distinguish them from JavaScript’s primitive types. Using this terminology, object values are references, and we say that objects are compared by reference: two object values are the same if and only if they refer to the same underlying object.
```
let a = []; // The variable a refers to an empty array.
let b = a; // Now b refers to the same array.
b[0] = 1; // Mutate the array referred to by variable b.
a[0] // => 1: the change is also visible through
variable a.
a === b // => true: a and b refer to the same object,
so they are equal.
```

## 3.9 Type Conversions
![[Table 3-2. JavaScript type conversions.png]]![[Table  3-2. JavaScript type conversions.png]]

### 3.9.1 Conversions and Equality
JavaScript has two operators that test whether two values are equal. 
The “strict equality operator,” \=\=\=, does not consider its operands to be equal if they are not of the same type. And this is almost always the right operator to use when coding.

JS also defines the == operator with a flexible definition of equality.
Examples:
```
null == undefined // => true: These two values are treated as
equal.
"0" == 0 // => true: String converts to a number
before comparing.
0 == false // => true: Boolean converts to number
before comparing.
"0" == false // => true: Both operands convert to 0
before comparing!
```

> [!warning]
> Keep in mind that convertibility of one value to another does not imply equality of those two values.

### 3.9.2 Explicit Conversions
Although JavaScript performs many type conversions automatically, you may sometimes need to perform an explicit conversion, or you may prefer to make the conversions explicit to keep your code clearer.

The simplest way to perform an explicit type conversion is to use the Boolean(), Number(), and String() functions:
```
Number("3") // => 3
String(false) // => "false": Or use false.toString()
Boolean([]) // => true
```

Certain JavaScript operators perform implicit type conversions and are sometimes used explicitly for the purpose of type conversion.
```
x + "" // => String(x)
+x // => Number(x)
x-0 // => Number(x)
!!x // => Boolean(x): Note double !
```

### 3.9.3 Object to Primitive Conversions
**OBJECT-TO-BOOLEAN CONVERSIONS**
All objects convert to true including empty arrays.

**OBJECT-TO-STRING CONVERSIONS**


**OBJECT-TO-NUMBER CONVERSIONS**


**SPECIAL CASE OPERATOR CONVERSIONS**
end of page 117




## 3.10 Variable Declaration and Assignment

### 3.10.1 Declarations with let and const
```
let i;
let sum;
\\or like this 
let i, sum;

```
It is a good programming practice to assign an initial value to your variables when you declare them, when this is possible:

An uninitialized variable has the value `undefined`.

To declare a constant instead of a variable, use const instead of let. const works just like let except that you must initialize the constant when you declare it:

It is a common (but not universal) convention to declare constants using names with all capital letters such as H0 or HTTP_NOT_FOUND as a way to distinguish them from variables.

> [!important] WHEN TO USE CONST
There are two schools of thought about the use of the const keyword. One approach is to use const only for values that are fundamentally unchanging, like the physical constants shown, or program version numbers, or byte sequences used to identify file types, for example. Another approach recognizes that many of the so-called variables in our program don’t actually ever change as our program runs. In this approach, we declare everything with const, and then if we find that we do actually want to allow the value to vary, we switch the declaration to let. This may help prevent bugs by ruling out accidental changes to variables that we did not intend. In one approach, we use const only for values that must not change. In the other, we use const for any value that does not happen to change. I prefer the former approach in my own code.


**VARIABLE AND CONSTANT SCOPE**
The scope of a variable is the region of your program source code in which it is defined.
Variables and constants declared with let and const are block scoped.

Roughly speaking, if a variable or constant is declared within a set of curly braces, then those curly braces delimit the region of code in which the variable or constant is defined.

## 3.11 Summary
Some key points to remember about this chapter:
* How to write and manipulate numbers and strings of text in JavaScript.
* How to work with JavaScript’s other primitive types: booleans, Symbols, null, and undefined.
* The differences between immutable primitive types and mutable reference types.
* How JavaScript converts values implicitly from one type to another and how you can do so explicitly in your programs.
* How to declare and initialize constants and variables(including with destructuring assignment) and the lexical scope of the variables and constants you declare.
_____
# Chapter 4. Expressions and Operators

> [!def] Definition: Expression
An expression is a phrase of JavaScript that can be evaluated to produce a value.

## 4.7 Operator Overview
![[Table 4-1. JavaScript operators 1.png]]
![[Table 4-1.  JavaScript operators 2.png]]
![[Table 4-1.   JavaScript operators 3.png]]


## 4.8 Arithmetic Expressions
if either operand is (or converts to) NAN the result of the operation is (almost always) NaN.

In JavaScript, all numbers are floating-point.

### 4.8.1 The + Operator
The binary + operator adds numeric operands or concatenates string operands.

The conversion rules for + give priority to string concatenation: if either of the operands is a string or an object that converts to a string, the other operand is converted to a string and concatenation is performed.


## 4.9 Relational Expressions


### 4.9.1 Equality and Inequality Operators
The == and === operators check whether two values are the same, using two different definitions of sameness.

== allows type conversion, The === operator is known as
the strict equality operator and does not allow type conversion.

The != and !== operators test for the exact opposite of the == and === operators.

The != inequality operator returns false if two values are equal to each other according to == and returns true otherwise. The !== operator returns false if two values are strictly equal to each other and returns true otherwise.

> [!important] THE =, \==, AND =\=\= OPERATORS
> JavaScript supports =, \=\=, and \=\=\= operators. Be sure you understand the differences between these assignment, equality, and strict equality operators, and be careful to use the correct one when coding! Although it is tempting to read all three operators as “equals,” it may help to reduce confusion if you read “gets” or “is assigned” for =, “is equal to” for \==, and “is strictly equal to” for =\=\=. The \== operator is a legacy feature of JavaScript and is widely considered to be a source of bugs. You should almost always use === instead of \=\=, and !\=\= instead of !=.

## 4.11 Assignment Expressions


## 4.13 Miscellaneous Operators

### 4.13.2 First-Defined (??)
The first-defined operator ?? evaluates to its first defined operand: if its left operand is not null and not undefined, it returns that value. Otherwise, it returns the value of the right operand. The ?? is an alternative to ||, as the problem with the || is that  zero, the empty string, and false are all falsy values that may be perfectly valid in some circumstances.

### 4.13.3 The typeof Operator
`typeof` is a unary operator that is placed before its single operand, which can be of any type. Its value is a string that specifies the type of the operand.
![[Table 4-3. Values returned by the typeof operator 1.png]]![[Table 4-3. Values returned by the typeof operator 2.png]]

### 4.13.4 The delete Operator
`delete` is a unary operator that attempts to delete the object property or array element specified as its operand.

`delete` expects its operand to be an lvalue. If it is not an lvalue, the operator takes no action and returns `true`. Otherwise, delete attempts to delete the specified lvalue. delete returns `true` if it successfully deletes the specified lvalue.

Deleting an array element leaves a “hole” in the array and does not change the array’s length. The resulting array is sparse.
```
let o = {x: 1, y: 2};
delete o.x; // Delete one of the object properties; returns
true.
typeof o.x; // Property does not exist; returns
"undefined".
delete o.x; // Delete a nonexistent property; returns true.
delete 1; // This makes no sense, but it just returns
true.
// Can't delete a variable; returns false, or SyntaxError in
strict mode.
delete o;
// Undeletable property: returns false, or TypeError in
strict mode.
delete Object.prototype;
```

### 4.13.5 The await Operator
see Chapter 13 for full details.

### 4.13.6 The void Operator
`void` is a unary operator that appears before its single operand, which may be of any type. This operator is unusual and infrequently used; it evaluates its operand, then discards the value and returns undefined. Since the operand value is discarded, using the `void` operator makes sense only if the operand has side effects.

The void operator is so obscure that it is difficult to come up with a practical example of its use. The example is at the end of page 194.


### 4.13.7 The comma Operator (,)
The comma operator is a binary operator whose operands may be of any type. It evaluates its left operand, evaluates its right operand, and then returns the value of the right operand.
```
i=0, j=1, k=2;
```
evaluates to 2 and is basically equivalent to:
```
i = 0; j = 1; k = 2;
```
The lefthand expression is always evaluated, but its value is discarded, which means that it only makes sense to use the comma operator when the lefthand expression has side effects. The only situation in which the comma operator is commonly used is with a for loop that has multiple loop variables:

## 4.14 Summary
This chapter covers a wide variety of topics, and there is lots of
reference material here that you may want to reread in the future as you continue to learn JavaScript. Some key points to remember, however, are these:

* Expressions are the phrases of a JavaScript program.
* Any expression can be evaluated to a JavaScript value.
* Expressions can also have side effects (such as variable assignment) in addition to producing a value.
* Simple expressions such as literals, variable references, and property accesses can be combined with operators to produce larger expressions.
* JavaScript defines operators for arithmetic, comparisons, Boolean logic, assignment, and bit manipulation, along with some miscellaneous operators, including the ternary conditional operator.
* The JavaScript + operator is used to both add numbers and concatenate strings.
* The logical operators && and || have special “short-circuiting” behaviour and sometimes only evaluate one of their arguments. Common JavaScript idioms require you to understand the special behaviour of these operators.
___
# Chapter 5. Statements
JavaScript statements are terminated with semicolons. Expressions are evaluated to produce a value, but statements are executed to make something happen.

## 5.1 Expression Statements

## 5.2 Compound and Empty Statements
statement block is simply a sequence of statements enclosed within curly braces.

## 5.3 Conditionals


### 5.3.1 if
The rule in JavaScript (as in most programming languages) is that by default an else clause is part of the nearest if statement.

### 5.3.3 switch
(When using switch inside a function, however, you may use a return statement instead of a break statement. Both serve to terminate the switch statement and prevent execution from falling through to the next case.)

## 5.4 Loops

### 5.4.2 do/while
The do/while loop is like a while loop, except that the loop expression is tested at the bottom of the loop rather than at the top. This means that the body of the loop is always executed at least once. The syntax is:
```
do
statement
while (expression);
```
the do loop must always be terminated with a semicolon. The while loop doesn’t need a semicolon if the loop body is enclosed in curly braces.

## 5.5

### 5.5.4 return
A return statement may appear only within the body of a function. It is a syntax error for it to appear anywhere else.


## 5.7 Declarations
The keywords const, let, var, function, class, import, and
export are declarations.

## 5.8 Summary of JavaScript Statements
This chapter introduced each of the JavaScript language’s statements, which are summarized in Table 5-1.
![[Table 5-1. JavaScript statement syntax 1.png]]
![[Table 5-1. JavaScript statement syntax 2.png]]
___
