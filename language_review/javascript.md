## JS Tutorial
### JS Introduction
### JS Where To
### JS Output
```js
console.log(5 + 6);
```
### JS Statements
A computer program is a list of "instructions" to be "executed" by a computer.
In a programming language, these programming instructions are called statements.
```js
let a, b, c;  // Declare 3 variables
a = 5;        // Assign the value 5 to a
b = 6;        // Assign the value 6 to b
c = a + b;    // Assign the sum of a and b to c
```
For best readability, programmers often like to avoid code lines longer than 80 characters.
### JS Syntax
All JavaScript identifiers are case sensitive. 
JavaScript programmers tend to use camel case that starts with a lowercase letter:  
firstName, lastName, masterCard, interCity.
### JS Comments
Single line comments start with //.
Multi-line comments start with /* and end with */.
Using comments to prevent execution of code is suitable for code testing.
```js
//document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
/*
document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
*/
```
### JS Variables
Only use let if you can't use const
Only use var if you MUST support old browsers.
A variable declared without a value will have the value `undefined`.
You cannot re-declare a variable declared with `let` or `const`.
```js
let person = "John Doe",
carName = "Volvo",
price = 200;
```
Using the dollar sign is not very common in JavaScript, but professional programmers often use it as an alias for the main function in a JavaScript library.
Using the underscore is not very common in JavaScript, but a convention among professional programmers is to use it as an alias for "private (hidden)" variables.
### JS Let
Before ES6 (2015), JavaScript did not have Block Scope.
JavaScript had Global Scope and Function Scope. ES6 introduced the two new JavaScript keywords: let and const.
These two keywords provided Block Scope in JavaScript
```js
var x = 10;
// Here x is 10

{
var x = 2;
// Here x is 2
}

// Here x is 2
```
#### What is Good?
`let` and `const` have block scope.
`let` and `const` can not be redeclared.
`let` and `const` must be declared before use.
`let` and `const` does not bind to this.
`let` and `const` are not hoisted.
#### What is Not Good?
`var` does not have to be declared.
`var` is hoisted.
`var` binds to this.
### JS Const",
The const keyword was introduced in ES6 (2015)   
Variables defined with const cannot be Redeclared   
Variables defined with const cannot be Reassigned
Variables defined with const have Block Scope

Always declare a variable with const when you know that the value should not be changed.
Use const when you declare:
- A new Array
- A new Object
- A new Function
- A new RegExp

The keyword const is a little misleading.
It does not define a constant value. It defines a constant reference to a value.
Because of this you **can NOT**:
- Reassign a constant value
- Reassign a constant array
- Reassign a constant object
But you **CAN**:
- Change the elements of constant array
- Change the properties of constant object

### JS Operators
There are different types of JavaScript operators:
- Arithmetic Operators
- Assignment Operators
- Comparison Operators
- String Operators
- Logical Operators
- Bitwise Operators
- Ternary Operators
- Type Operators (`typeof`, `instanceof`)

### JS Arithmetic
```js
let x = 5;
let y = 2;
let z = x + y;
let z = x - y;
let z = x * y;
let z = x / y;
let z = x % y;
x++;
x--;
let z = x ** 2;
let z = Math.pow(x,2);
```
### JS Assignment
```js
let x = 10;
x += 5;
x -= 5;
x -= 5;
x *= 5;
x **= 5;
x /= 5;
x %= 5;

let x = -100;
x <<= 5;
x >>= 5;
x >>>= 5;
x &= 5;
x |= 5;
x ^= 5;
x &&= 5; //The &&= operator is an ES2020 feature. If the first value is true, the second value is assigned.
x ||= 5; //The ||= operator is an ES2020 feature. If the first value is false, the second value is assigned.
x ??= 5; //The ??= operator is an ES2020 feature. If the first value is undefined or null, the second value is assigned.
```

### JS Data Types
JavaScript has 8 Datatypes
1. String
2. Number
3. Bigint
4. Boolean
5. Undefined
6. Null
7. Symbol
8. Object

The Object Datatype
The object data type can contain:
1. An object
2. An array
3. A date

```js
// Numbers:
let length = 16;
let weight = 7.5;

// Strings:
let color = "Yellow";
let lastName = "Johnson";

// Booleans
let x = true;
let y = false;

// Object:
const person = {firstName:"John", lastName:"Doe"};

// Array object:
const cars = ["Saab", "Volvo", "BMW"];

// Date object:
const date = new Date("2022-03-25");
```

When adding a number and a string, JavaScript will treat the number as a string. JavaScript evaluates expressions from left to right. Different sequences can produce different results:
```js
let x = 16 + 4 + "Volvo"; //20Volvo
let x = "Volvo" + 16 + 4; //Volvo164
```

Javascript numbers are always one type:
**double** (64-bit floating point).

JavaScript BigInt is a new datatype (ES2020) that can be used to store integer values that are too big to be represented by a normal JavaScript Number.
```js
let x = BigInt("123456789012345678901234567890");
```

You can use the JavaScript `typeof` operator to find the type of a JavaScript variable.

In JavaScript, a variable without a value, has the value `undefined`. The type is also `undefined`.

### JS Functions


### JS Objects",
### JS Events",
### JS Strings",
### JS String Methods",
### JS String Search",
### JS String Templates",
### JS Numbers",
### JS BigInt",
### JS Number Methods",
### JS Number Properties",
### JS Arrays",
### JS Array Methods",
### JS Array Search",
### JS Array Sort",
### JS Array Iteration",
### JS Array Const",
### JS Dates",
### JS Date Formats",
### JS Date Get Methods",
### JS Date Set Methods",
### JS Math",
### JS Random",
### JS Booleans",
### JS Comparisons",
### JS If Else",
### JS Switch",
### JS Loop For",
### JS Loop For In",
### JS Loop For Of",
### JS Loop While",
### JS Break",
### JS Iterables",
### JS Sets",
### JS Maps",
### JS Typeof",
### JS Type Conversion",
### JS Bitwise",
### JS RegExp",
### JS Precedence",
### JS Errors",
### JS Scope",
### JS Hoisting",
### JS Strict Mode",
### JS this Keyword",
### JS Arrow Function",
### JS Classes",
### JS Modules",
### JS JSON",
### JS Debugging",
### JS Style Guide",
### JS Best Practices",
### JS Mistakes",
### JS Performance",
### JS Reserved Words",
### JS Versions",
### JS 2009 (ES5)",
### JS 2015 (ES6)",
### JS 2016",
### JS 2017",
### JS 2018",
### JS 2019",
### JS 2020",
### JS 2021",
### JS 2022",
### JS 2023",
### JS IE / Edge",
### JS History",
### Object Definitions",
### Object Properties",
### Object Methods",
### Object Display",
### Object Accessors",
### Object Constructors",
### Object Prototypes",
### Object Iterables",
### Object Sets",
### Object Maps",
### Object Reference",
### Function Definitions",
### Function Parameters",
### Function Invocation",
### Function Call",
### Function Apply",
### Function Bind",
### Function Closures",
### Class Intro",
### Class Inheritance",
### Class Static",
### JS Callbacks",
### JS Asynchronous",
### JS Promises",
### JS Async/Await",
### DOM Intro",
### DOM Methods",
### DOM Document",
### DOM Elements",
### DOM HTML",
### DOM Forms",
### DOM CSS",
### DOM Animations",
### DOM Events",
### DOM Event Listener",
### DOM Navigation",
### DOM Nodes",
### DOM Collections",
### DOM Node Lists",
### JS Window",
### JS Screen",
### JS Location",
### JS History",
### JS Navigator",
### JS Popup Alert",
### JS Timing",
### JS Cookies",
### Web API Intro",
### Web Forms API",
### Web History API",
### Web Storage API",
### Web Worker API",
### Web Fetch API",
### Web Geolocation API",
### AJAX Intro",
### AJAX XMLHttp",
### AJAX Request",
### AJAX Response",
### AJAX XML File",
### AJAX PHP",
### AJAX ASP",
### AJAX Database",
### AJAX Applications",
### AJAX Examples",
### JSON Intro",
### JSON Syntax",
### JSON vs XML",
### JSON Data Types",
### JSON Parse",
### JSON Stringify",
### JSON Objects",
### JSON Arrays",
### JSON Server",
### JSON PHP",
### JSON HTML",
### JSON JSONP",
### jQuery Selectors",
### jQuery HTML",
### jQuery CSS",
### jQuery DOM",
### JS Graphics",
### JS Canvas",
### JS Plotly",
### JS Chart.js",
### JS Google Chart",
### JS D3.js",
### JS Examples",
### JS HTML DOM",
### JS HTML Input",
### JS HTML Objects",
### JS HTML Events",
### JS Browser",
### JS Editor",
### JS Exercises",
### JS Quiz",
### JS Website",
### JS Bootcamp",
### JS Certificate",
### JavaScript Objects",
### HTML DOM Objects"