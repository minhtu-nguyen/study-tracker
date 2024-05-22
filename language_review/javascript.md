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
The code inside the function will execute when "something" invokes (calls) the function:   
When an event occurs (when a user clicks a button)   
When it is invoked (called) from JavaScript code   
Automatically (self invoked)   

Variables declared within a JavaScript function, become LOCAL to the function.
```js
// Function is called, the return value will end up in x
let x = myFunction(4, 3);
// code here can NOT use carName
function myFunction(a, b) {
  let carName = "Volvo";
// Function returns the product of a and b
  return a * b;
}
```

### JS Objects
Objects are variables too. But objects can contain many values.
It is a common practice to declare objects with the const keyword.
```js
const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```
#### What is this?
The this keyword refers to different objects depending on how it is used:
- In an object method, this refers to the object.
- Alone, this refers to the global object.
- In a function, this refers to the global object.
- In a function, in strict mode, this is undefined.
- In an event, this refers to the element that received the event.
- Methods like call(), apply(), and bind() can refer this to any object.

Avoid String, Number, and Boolean objects. They complicate your code and slow down execution speed.

### JS Events
HTML events are "things" that happen to HTML elements.
When JavaScript is used in HTML pages, JavaScript can "react" on these events.

### JS Strings
Strings created with single or double quotes works the same.
There is no difference between the two.

Templates were introduced with ES6 (JavaScript 2016).

All string methods return a new string. They don't modify the original string.   
Strings are immutable: Strings cannot be changed, only replaced.
```js
let text = `He's often called "Johnny"`;
let text2 = "We are the so-called \"Vikings\" from the north.";
```
### JS String Methods
```js
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;

let text = "HELLO WORLD";
let char = text.charAt(0);
let char = text.charCodeAt(0);
//ES2022 introduced the string method at(). It allows the use of negative indexes while charAt() do not.
const name = "W3Schools";
let letter = name.at(2);
/* Property access
Property access might be a little unpredictable:

It makes strings look like arrays (but they are not)
If no character is found, [ ] returns undefined, while charAt() returns an empty string.
It is read only. str[0] = "A" gives no error (but does not work!)
*/
let letter = name[2];
let text = "HELLO WORLD";
text[0] = "A";    // Gives no error, but does not work

let text = "Apple, Banana, Kiwi";
let part = text.slice(7, 13);
let part = text.slice(7);
let part = text.slice(-12);
let part = text.slice(-12, -6);
//substring() is similar to slice(). The difference is that start and end values less than 0 are treated as 0 in substring().
let part = str.substring(7, 13);
//substr() is similar to slice(). The difference is that the second parameter specifies the length of the extracted part.
let part = str.substr(7, 6);
let part = str.substr(7);
let part = str.substr(-4);

let text1 = "Hello World!";
let text2 = text1.toUpperCase();
let text2 = text1.toLowerCase();
text = "Hello" + " " + "World!";
text = "Hello".concat(" ", "World!");

let text1 = "      Hello World!      ";
let text2 = text1.trim();
let text2 = text1.trimStart();
let text2 = text1.trimEnd();

//padStart() is an ECMAScript 2017 feature.
let text = "5";
let padded = text.padStart(4,"0");
//To pad a number, convert the number to a string first.
let numb = 5;
let text = numb.toString();
let padded = text.padStart(4,"0");

//repeat() is an ES6 feature (JavaScript 2015).
let text = "5";
let padded = text.padEnd(4,"0");
let numb = 5;
let text = numb.toString();
let padded = text.padEnd(4,"0");

let text = "Hello world!";
let result = text.repeat(2);

//The replace() method replaces only the first match. If you want to replace all matches, use a regular expression with the /g flag set.
let text = "Please visit Microsoft and Microsoft!";
let newText = text.replace(/MICROSOFT/i, "W3Schools");
let newText = text.replace(/Microsoft/g, "W3Schools");

//replaceAll() is an ES2021 feature.
text = text.replaceAll(/Cats/g,"Dogs");

text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe
text.split("")     // the returned array will be an array of single characters
```

### JS String Search
```js
let text = "Please locate where 'locate' occurs!";
let index = text.indexOf("locate");
let index = text.indexOf("locate", 15);
let index = text.lastIndexOf("locate");
text.lastIndexOf("locate", 15);

let text = "Please locate where 'locate' occurs!";
text.search(/locate/);

let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/gi);
// matchAll() is an ES2020 feature.
const iterator = text.matchAll(/Cats/gi);
// case sensitive. ES6 feature.
let text = "Hello world, welcome to the universe.";
text.includes("world", 12);

let text = "Hello world, welcome to the universe.";
text.startsWith("world", 5)
let text = "Hello world, welcome to the universe.";
text.endsWith("world", 11);
```

### JS String Templates
Automatic replacing of variables with real values is called string interpolation.
```js
let price = 10;
let VAT = 0.25;

let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;
```

### JS Numbers
JavaScript does not define different types of numbers, like integers, short, long, floating-point etc.

JavaScript numbers are always stored as double precision floating point numbers, following the international IEEE 754 standard.

This format stores numbers in 64 bits, where the number (the fraction) is stored in bits 0 to 51, the exponent in bits 52 to 62, and the sign in bit 63.

Integers (numbers without a period or exponent notation) are accurate up to 15 digits. The maximum number of decimals is 17.

Floating point arithmetic is not always 100% accurate. To solve the problem above, it helps to multiply and divide.
```js
let x = (0.2 * 10 + 0.1 * 10) / 10;
```
JavaScript uses the + operator for both addition and concatenation. Numbers are added. Strings are concatenated.
```js
let x = 10;
let y = 20;
let z = "The result is: " + x + y;

let x = 10;
let y = 20;
let z = "30";
let result = x + y + z;
```

NaN is a JavaScript reserved word indicating that a number is not a legal number.
```js
let x = 100 / "Apple";
```
NaN is a number: typeof NaN returns number.
Infinity (or -Infinity) is the value JavaScript will return if you calculate a number outside the largest possible number. Division by 0 (zero) also generates Infinity. Infinity is a number: typeof Infinity returns number.
```js
let y = -2 / 0;
```
JavaScript interprets numeric constants as hexadecimal if they are preceded by 0x. Never write a number with a leading zero (like 07). Some JavaScript versions interpret numbers as octal if they are written with a leading zero.  
By default, JavaScript displays numbers as base 10 decimals. But you can use the toString() method to output numbers from base 2 to base 36.
```js
let x = 0xFF;

let myNumber = 32;
myNumber.toString(32);
myNumber.toString(16);
myNumber.toString(12);
myNumber.toString(10);
myNumber.toString(8);
myNumber.toString(2);
```
### JS BigInt
64-bit floating-point format (IEEE 754 standard).
With this standard, large integer cannot be exactly represented and will be rounded.
To create a BigInt, append n to the end of an integer or call BigInt():
```js
let x = 1234567890123456789012345n;
let y = BigInt(1234567890123456789012345)
let type = typeof x; //
let y = x / 2; // A BigInt can not have decimals. Error: Cannot mix BigInt and other types, use explicit conversion.

let hex = 0x20000000000003n;
let oct = 0o400000000000000003n;
let bin = 0b100000000000000000000000000000000000000000000000000011n;
```
With BigInt the total number of supported data types in JavaScript is 8.
ES6 added max and min properties to the Number object:
`MAX_SAFE_INTEGER`   
`MIN_SAFE_INTEGER`  
`Number.isInteger()`   
`Number.isSafeInteger()`   

### JS Number Methods
If the number cannot be converted, `NaN` (Not a Number) is returned.
```js
let x = 123;
x.toString();
(123).toString();

let x = 9.656;
x.toExponential(2);

let x = 9.656;
x.toFixed(0);
x.toFixed(2);

let x = 9.656;
x.toPrecision();
x.toPrecision(2);

let x = 123;
x.valueOf();
(123).valueOf();

Number(false);
Number("10");
Number("John");
Number(new Date("1970-01-01"))

parseInt("-10");
parseInt("10 20 30");
parseInt("years 10");
Number.parseInt("-10");

parseFloat("10");
parseFloat("10.33");
parseFloat("10 20 30");
parseFloat("10 years");
parseFloat("years 10");
Number.parseFloat("10.33");

Number.isInteger(10);
Number.isInteger(10.5);

Number.isSafeInteger(12345678901234567890);
```

### JS Number Properties
```js
let x = Number.EPSILON;
let x = Number.MAX_VALUE;
let x = Number.MIN_VALUE;
let x = Number.MAX_SAFE_INTEGER;
let x = Number.MIN_SAFE_INTEGER;
let x = Number.POSITIVE_INFINITY;
let x = Number.NEGATIVE_INFINITY;
let x = Number.NaN;
```

### JS Arrays
```js
const cars = new Array("Saab", "Volvo", "BMW");
const cars = ["Saab", "Volvo", "BMW"];
let car = cars[0];
cars[0] = "Opel";
cars.length   // Returns the number of elements
cars.sort()   // Sorts the array

const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits[0];
let fruit = fruits[fruits.length - 1];
fruits.push("Lemon");  // Adds a new element (Lemon) to fruits
fruits[fruits.length] = "Lemon";  // Adds "Lemon" to fruits
fruits[6] = "Lemon";  // Creates undefined "holes" in fruits
```
Arrays are a special type of objects. The `typeof` operator in JavaScript returns "object" for arrays.
```js
const fruits = ["Banana", "Orange", "Apple"];
let type = typeof fruits;

Array.isArray(fruits);
fruits instanceof Array;
```

In JavaScript, arrays use numbered indexes.  
In JavaScript, objects use named indexes.   
If you use named indexes, JavaScript will redefine the array to an object.
```js
const person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
person.length;     // Will return 0
person[0];         // Will return undefined

// Create an array with one element:
const points = [40];
// Create an array with 40 undefined elements:
const points = new Array(40);  
```

### JS Array Methods
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let size = fruits.length;

//ES2022 intoduced the array method at():
let fruit = fruits.at(2);
```
Many languages allows negative bracket indexing like `[-1]` to access elements from the end of an object / array / string.

This is not possible in JavaScript, because `[]` is used for accessing both arrays and objects. obj[-1] refers to the value of key -1, not to the last property of the object.

The `at()` method was introduced in ES2022 to solve this problem.

```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.join(" * ");
fruits.pop(); //removes the last element from an array
let fruit = fruits.pop(); //returns the value that was "popped out"

fruits.push("Kiwi");
let length = fruits.push("Kiwi"); //new array length


fruits.shift(); //removes the first array element
let fruit = fruits.shift();

fruits.unshift("Lemon"); //adds a new element to an array (at the beginning)
fruits.unshift("Lemon");

fruits[0] = "Kiwi";
fruits[fruits.length] = "Kiwi"; //append a new element to an array

delete fruits[0]; //leaves undefined holes in the array. Use pop() or shift() instead.

const myGirls = ["Cecilie", "Lone"];
const myBoys = ["Emil", "Tobias", "Linus"];
const myChildren = myGirls.concat(myBoys); //returns a new array
const arr3 = ["Robin", "Morgan"];
const myChildren = arr1.concat(arr2, arr3);
const myChildren = arr1.concat("Peter"); 

const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0); //The copyWithin() method overwrites the existing values.

const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat(); //ES2019 Introduced the Array flat() method

/*
The first parameter (2) defines the position where new elements should be added (spliced in).

The second parameter (0) defines how many elements should be removed.

The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be added.

The splice() method returns an array with the deleted items
*/
fruits.splice(2, 0, "Lemon", "Kiwi");
fruits.splice(0, 1); //remove elements without leaving "holes" 
```
ES2023 added the Array toSpliced() method as a safe way to splice an array without altering the original array.

The difference between the new toSpliced() method and the old splice() method is that the new method creates a new array, keeping the original array unchanged, while the old method altered the original array.
```js
const months = ["Jan", "Feb", "Mar", "Apr"];
const spliced = months.toSpliced(0, 1);
```

The slice() method creates a new array.   
The slice() method does not remove any elements from the source array.
```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(3);
const citrus = fruits.slice(1, 3);
```
### JS Array Search
```js
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.indexOf("Apple") + 1;
let position = fruits.lastIndexOf("Apple") + 1;
fruits.includes("Mango"); // is true

const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction); //find() is an ES6 feature (JavaScript 2015).
let first = numbers.findIndex(myFunction); //findIndex() is an ES6 feature (JavaScript 2015).
function myFunction(value, index, array) {
  return value > 18; 
}

const temp = [27, 28, 30, 40, 42, 35, 30];
let high = temp.findLast(x => x > 40); //findLast() is an ES2023 feature.
let pos = temp.findLastIndex(x => x > 40); //findLastIndex() is an ES2023 feature.
```

### JS Array Sort
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();
fruits.reverse();

//ES2023 added the toSorted(), toReversed() --> new array
const months = ["Jan", "Feb", "Mar", "Apr"];
const sorted = months.toSorted();
const reversed = months.toReversed();

const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a - b}); //return a negative, zero, or positive value
points.sort(function(a, b){return b - a});
points.sort(function(){return 0.5 - Math.random()});

Math.min.apply(null, [1, 2, 3]) //is equivalent to Math.min(1, 2, 3).
Math.max.apply(null, [1, 2, 3]) //is equivalent to Math.max(1, 2, 3).
```
Fisher Yates Method
```js
const points = [40, 100, 1, 5, 25, 10];

for (let i = points.length -1; i > 0; i--) {
  let j = Math.floor(Math.random() * (i+1));
  let k = points[i];
  points[i] = points[j];
  points[j] = k;
}
```

Sorting Object Arrays

```js
const cars = [
  {type:"Volvo", year:2016},
  {type:"Saab", year:2001},
  {type:"BMW", year:2010}
];

cars.sort(function(a, b){return a.year - b.year});
```

Stable Array sort()
Before 2019, the specification allowed unstable sorting algorithms such as QuickSort.
After ES2019, browsers must use a stable sorting algorithm:
When sorting elements on a value, the elements must keep their relative position to other elements with the same value.
```js
const myArr = [
  {name:"X00",price:100 },
  {name:"X01",price:100 },
  {name:"X02",price:100 },
  {name:"X03",price:100 },
  {name:"X04",price:110 },
  {name:"X05",price:110 },
  {name:"X06",price:110 },
  {name:"X07",price:110 }
];

X01 100
X03 100
X00 100
X03 100
X05 110
X04 110
X06 110
X07 110
```
### JS Array Iteration
```js
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);
function myFunction(value) {
  txt += value + "<br>";
}

const numbers1 = [45, 4, 9, 16, 25];
const numbers2 = numbers1.map(myFunction); //The map() method does not change the original array
function myFunction(value) {
  return value * 2;
}

const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap((x) => x * 2); //ES2019 added the Array flatMap(). New array by flattening the array.

const numbers = [45, 4, 9, 16, 25];
const over18 = numbers.filter(myFunction);
function myFunction(value) {
  return value > 18;
}

const numbers = [45, 4, 9, 16, 25];
let sum = numbers.reduce(myFunction);
let sum = numbers.reduce(myFunction, 100);
let sum = numbers.reduceRight(myFunction);
function myFunction(total, value) {
  return total + value;
}

const numbers = [45, 4, 9, 16, 25];
let allOver18 = numbers.every(myFunction); //all array values pass a test
let someOver18 = numbers.some(myFunction); //some array values pass a test.
function myFunction(value) {
  return value > 18;
}

Array.from("ABCDEFG"); //returns an Array object from any object with a length property or any iterable object

const months = ["Januar", "Februar", "Mar", "April"];
const myMonths = months.with(2, "March"); //ES2023, new array

const q1 = ["Jan", "Feb", "Mar"];
const q2 = ["Apr", "May", "Jun"];
const q3 = ["Jul", "Aug", "Sep"];
const q4 = ["Oct", "Nov", "May"];
const year = [...q1, ...q2, ...q3, ...q4]; //spread
```
### JS Array Const
```js
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
// You can change an element:
cars[0] = "Toyota";
// You can add an element:
cars.push("Audi");

const cars = ["Saab", "Volvo", "BMW"];
// Here cars[0] is "Saab"
{
  const cars = ["Toyota", "Volvo", "BMW"];
  // Here cars[0] is "Toyota"
}
// Here cars[0] is "Saab"

var cars = ["Volvo", "BMW"];     // Allowed
const cars = ["Volvo", "BMW"];   // Not allowed
{
  var cars = ["Volvo", "BMW"];   // Allowed
  const cars = ["Volvo", "BMW"]; // Not allowed
}
```
### JS Dates
7 numbers specify year, month, day, hour, minute, second, and millisecond (in that order).
Specifying a day higher than max, will not result in an error but add the overflow to the next month.
One and two digit years will be interpreted as 19xx
```js
const d = new Date(99, 11, 24);
d.toString();
d.toDateString();
d.toUTCString();
d.toISOString();
```

### JS Date Formats
Date Input
ISO Date	"2015-03-25" (The International Standard)
Short Date	"03/25/2015"
Long Date	"Mar 25 2015" or "25 Mar 2015"
The ISO 8601 syntax (YYYY-MM-DDTHH:MM:SSZ) is also the preferred JavaScript date format
UTC time is defined with a capital letter Z.
If you want to modify the time relative to UTC, remove the Z and add +HH:MM or -HH:MM instead
```js
const d = new Date("2015-03-25");
const d = new Date("2015-03-25T12:00:00Z");
const d = new Date("2015-03-25T12:00:00-06:30");

let msec = Date.parse("March 21, 2012"); //returns the number of milliseconds between the date and January 1, 1970
const d = new Date(msec);
```
### JS Date Get Methods
getYear() is deprecated. Do not use it!
```js
const d = new Date();
d.getFullYear();

d.getMonth();
const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
let month = months[d.getMonth()];

d.getDate();
d.getHours();
d.getMinutes();
d.getSeconds();
d.getMilliseconds();

d.getDay();
const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
let day = days[d.getDay()];

d.getTime();
let ms = Date.now(); //milliseconds since January 1, 1970
```
### JS Date Set Methods
```js
const d = new Date();
d.setFullYear(2020);
d.setFullYear(2020, 11, 3);
d.setMonth(11);
d.setDate(15);
d.setDate(d.getDate() + 50);
d.setHours(22);
d.setMinutes(30);
d.setSeconds(30);
```
### JS Math
```js
Math.E        // returns Euler's number
Math.PI       // returns PI
Math.SQRT2    // returns the square root of 2
Math.SQRT1_2  // returns the square root of 1/2
Math.LN2      // returns the natural logarithm of 2
Math.LN10     // returns the natural logarithm of 10
Math.LOG2E    // returns base 2 logarithm of E
Math.LOG10E   // returns base 10 logarithm of E

Math.round(4.6);
Math.ceil(4.2);
Math.floor(4.7);
Math.trunc(4.4); //integer part of x
Math.sign(-4);
Math.pow(8, 2);
Math.sqrt(64);
Math.abs(-4.7);
Math.sin(90 * Math.PI / 180);     // returns 1 (the sine of 90 degrees)
Math.cos(0 * Math.PI / 180);     // returns 1 (the cos of 0 degrees)
Math.min(0, 150, 30, 20, -8, -200);
Math.max(0, 150, 30, 20, -8, -200);
Math.random(); //between 0 (inclusive), and 1 (exclusive)
Math.log(3);
Math.log2(8);
Math.log10(1000);
```

### JS Random
```js
// Returns a random integer from 0 to 9:
Math.floor(Math.random() * 10);
// Returns a random integer from 0 to 10:
Math.floor(Math.random() * 11);
// Returns a random integer from 1 to 10:
Math.floor(Math.random() * 10) + 1;
// min (included) and max (excluded)
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min) ) + min;
}
// min and max (both included)
function getRndInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1) ) + min;
}
```
### JS Booleans
```js
// false
let x = 0;
Boolean(x);
let x = "";
Boolean(x);
let x; // undefined
Boolean(x);
let x = null;
Boolean(x);
let x = 10 / "Hallo"; // NaN
Boolean(x);
```
### JS Comparisons
```js
let voteable = (age < 18) ? "Too young":"Old enough";

// ?? operator returns the first argument if it is not nullish (null or undefined)
let name = null;
let text = "missing";
let result = name ?? text;

// ?. operator returns undefined if an object is undefined or null (instead of throwing an error)
// Create an object:
const car = {type:"Fiat", model:"500", color:"white"};
// Ask for car name:
document.getElementById("demo").innerHTML = car?.name;
```
### JS If Else
```js
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}

```

### JS Switch
Switch cases use strict comparison (===). The values must be of the same type to match.
```js
switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Soon it is Weekend";
    break;
  case 0:
  case 6:
    text = "It is Weekend";
    break;
  default:
    text = "Looking forward to the Weekend";
}

let x = "0";
switch (x) {
  case 0:
    text = "Off";
    break;
  case 1:
    text = "On";
    break;
  default:
    text = "No value found";
}
```
### JS Loop For
for (expression 1; expression 2; expression 3) {
  // code block to be executed
}
Expression 1 is executed (one time) before the execution of the code block.
Expression 2 defines the condition for executing the code block.
Expression 3 is executed (every time) after the code block has been executed.
```js
for (let i = 0, len = cars.length, text = ""; i < len; i++) {
  text += cars[i] + "<br>";
}

var i = 5;
for (var i = 0; i < 10; i++) {
  // some code
}
// Here i is 10

let i = 5;
for (let i = 0; i < 10; i++) {
  // some code
}
// Here i is 5
```

### JS Loop For In
Do not use for in over an Array if the index order is important.
The index order is implementation-dependent, and array values may not be accessed in the order you expect.
It is better to use a for loop, a for of loop, or Array.forEach() when the order is important.
```js
const numbers = [45, 4, 9, 16, 25];

let txt = "";
for (let x in numbers) {
  txt += numbers[x];
}

numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt += value;
}
```

### JS Loop For Of
```js
const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text +=
}
```
### JS Loop While
```js
do {
  text += "The number is " + i;
  i++;
}
while (i < 10);
```
### JS Break
```js
for (let i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}

for (let i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}

label:
statements

const cars = ["BMW", "Volvo", "Saab", "Ford"];
list: {
  text += cars[0] + "<br>";
  text += cars[1] + "<br>";
  break list;
  text += cars[2] + "<br>";
  text += cars[3] + "<br>";
}
```
### JS Iterables
```js
// Create an Object
myNumbers = {};

// Make it Iterable
myNumbers[Symbol.iterator] = function() {
  let n = 0;
  done = false;
  return {
    next() {
      n += 10;
      if (n == 100) {done = true}
      return {value:n, done:done};
    }
  };
}

for (const num of myNumbers) {
  // Any Code Here
}
```
### JS Sets
```js
// Create a Set
const letters = new Set(["a","b","c"]);

// Create a Set
const letters = new Set();

// Add Values to the Set
letters.add("a");
letters.add("b");
letters.add("c");

// List all Elements
let text = "";
for (const x of letters) {
  text += x;
}
// List all entries
let text = "";
letters.forEach (function(value) {
  text += value;
})

// Get all Values
const myIterator = letters.values();
const myIterator = letters.keys(); // A Set has no keys, so keys() returns the same as values().
const myIterator = letters.entries(); // Iterator with [value,value]

// Does the Set contain "d"?
answer = letters.has("d");
```

### JS Maps
Map is an ES6 feature
```js
// Create a Map
const fruits = new Map();

// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200);

fruits.get("apples");    // Returns 500
fruits.clear();
fruits.set("apples", 500);
fruits.size;
fruits.delete("apples");
fruits.has("apples");

// List all entries
let text = "";
fruits.forEach (function(value, key) {
  text += key + ' = ' + value;
})

// List all entries
let text = "";
for (const x of fruits.entries()) {
  text += x;
}

// List all keys
let text = "";
for (const x of fruits.keys()) {
  text += x;
}

// List all values
let text = "";
for (const x of fruits.values()) {
  text += x;
}

// Create an Array
const fruits = [
  {name:"apples", quantity:300},
  {name:"bananas", quantity:500},
  {name:"oranges", quantity:200},
  {name:"kiwi", quantity:150}
];

// Callback function to Group Elements
function myCallback({ quantity }) {
  return quantity > 200 ? "ok" : "low";
}

// Group by Quantity
const result = Map.groupBy(fruits, myCallback);
```
Object.groupBy() groups elements into a JavaScript object.
Map.groupBy() groups elements into a Map object.


### JS Typeof
In JavaScript there are 5 different data types that can contain values:
`string`
`number`
`boolean`
`object`
`function`
There are 6 types of objects:
`Object`
`Date`
`Array`
`String`
`Number`
`Boolean`
And 2 data types that cannot contain values:
`null`
`undefined`
```js
typeof "John"                 // Returns "string"
typeof 3.14                   // Returns "number"
typeof NaN                    // Returns "number"
typeof false                  // Returns "boolean"
typeof [1,2,3,4]              // Returns "object"
typeof {name:'John', age:34}  // Returns "object"
typeof new Date()             // Returns "object"
typeof function () {}         // Returns "function"
typeof myCar                  // Returns "undefined" *
typeof null                   // Returns "object"

typeof "John"              // Returns "string"
typeof 3.14                // Returns "number"
typeof true                // Returns "boolean"
typeof false               // Returns "boolean"
typeof x                   // Returns "undefined" (if x has no value)

typeof {name:'John', age:34} // Returns "object"
typeof [1,2,3,4]             // Returns "object" (not "array", see note below)
typeof null                  // Returns "object"
typeof function myFunc(){}   // Returns "function"

"John".constructor                // Returns function String()  {[native code]}
(3.14).constructor                // Returns function Number()  {[native code]}
false.constructor                 // Returns function Boolean() {[native code]}
[1,2,3,4].constructor             // Returns function Array()   {[native code]}
{name:'John',age:34}.constructor  // Returns function Object()  {[native code]}
new Date().constructor            // Returns function Date()    {[native code]}
function () {}.constructor        // Returns function Function(){[native code]}

typeof undefined           // undefined
typeof null                // object

null === undefined         // false
null == undefined          // true
```

### JS Type Conversion
| Original<br>Value | Converted<br>to Number | Converted<br>to String | Converted<br>to Boolean | Try it                                                                                           |
| ----------------- | ---------------------- | ---------------------- | ----------------------- | ------------------------------------------------------------------------------------------------ |
| false             | 0                      | "false"                | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_false)             |
| true              | 1                      | "true"                 | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_true)              |
| 0                 | 0                      | "0"                    | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_number_0)          |
| 1                 | 1                      | "1"                    | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_number_1)          |
| "0"               | 0                      | "0"                    | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_0)          |
| "000"             | 0                      | "000"                  | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_000)        |
| "1"               | 1                      | "1"                    | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_1)          |
| NaN               | NaN                    | "NaN"                  | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_nan)               |
| Infinity          | Infinity               | "Infinity"             | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_infinity)          |
| \-Infinity        | \-Infinity             | "-Infinity"            | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_infinity_minus)    |
| ""                | 0                      | ""                     | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_empty)      |
| "20"              | 20                     | "20"                   | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_number)     |
| "twenty"          | NaN                    | "twenty"               | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_string_text)       |
| [ ]               | 0                      | ""                     | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_array_empty)       |
| [20]              | 20                     | "20"                   | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_array_one_number)  |
| [10,20]           | NaN                    | "10,20"                | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_array_two_numbers) |
| ["twenty"]        | NaN                    | "twenty"               | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_array_one_string)  |
| ["ten","twenty"]  | NaN                    | "ten,twenty"           | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_array_two_strings) |
| function(){}      | NaN                    | "function(){}"         | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_function)          |
| { }               | NaN                    | "[object Object]"      | true                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_object)            |
| null              | 0                      | "null"                 | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_null)              |
| undefined         | NaN                    | "undefined"            | false                   | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_type_convert_undefined)

<br>   |

### JS Bitwise
JavaScript stores numbers as 64 bits floating point numbers, but all bitwise operations are performed on 32 bits binary numbers. Before a bitwise operation is performed, JavaScript converts numbers to 32 bits signed integers.
After the bitwise operation is performed, the result is converted back to 64 bits JavaScript numbers.

| Operator | Name                  | Description                                                                                              |
| -------- | --------------------- | -------------------------------------------------------------------------------------------------------- |
| &        | AND                   | Sets each bit to 1 if both bits are 1                                                                    |
| \|       | OR                    | Sets each bit to 1 if one of two bits is 1                                                               |
| ^        | XOR                   | Sets each bit to 1 if only one of two bits is 1                                                          |
| ~        | NOT                   | Inverts all the bits                                                                                     |
| <<       | Zero fill left shift  | Shifts left by pushing zeros in from the right and let the leftmost bits fall off                        |
| \>>      | Signed right shift    | Shifts right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off |
| \>>>     | Zero fill right shift | Shifts right by pushing zeros in from the left, and let the rightmost bits fall off<br><br>              |

| Operation | Result | Same as      | Result |
| --------- | ------ | ------------ | ------ |
| 5 & 1     | 1      | 0101 & 0001  |  0001  |
| 5 \| 1    | 5      | 0101 \| 0001 |  0101  |
| ~ 5       | 10     |  ~0101       |  1010  |
| 5 << 1    | 10     | 0101 << 1    |  1010  |
| 5 ^ 1     | 4      | 0101 ^ 0001  |  0100  |
| 5 >> 1    | 2      | 0101 >> 1    |  0010  |
| 5 >>> 1   | 2      | 0101 >>> 1   |  0010  |

```js
function dec2bin(dec){
  return (dec >>> 0).toString(2);
}

function bin2dec(bin){
  return parseInt(bin, 2).toString(10);
}
```
### JS RegExp
`/pattern/modifiers;`
`/w3schools/i;`

| Modifier | Description                                                                                | Try it                                                                                |
| -------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| i        | Perform case-insensitive matching                                                          | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_i)            |
| g        | Perform a global match (find all)                                                          | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_g)            |
| m        | Perform multiline matching                                                                 | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_m)            |
| d        | Perform start and end matching (New in [ES2022](https://www.w3schools.com/js/js_2022.asp)) | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_inices)

<br> |

| Expression | Description                                     | Try it                                                                            |
| ---------- | ----------------------------------------------- | --------------------------------------------------------------------------------- |
| [abc]      | Find any of the characters between the brackets | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_abc)      |
| [0-9]      | Find any of the digits between the brackets     | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_0-9)      |
| (x\|y)     | Find any of the alternatives separated with \|  | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_xy)

<br> |

| Metacharacter | Description                                                                                            | Try it                                                                                                                                                    |
| ------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \\d           | Find a digit                                                                                           | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_d)                                                                                |
| \\s           | Find a whitespace character                                                                            | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_s)                                                                                |
| \\b           | Find a match at the beginning of a word like this: \\bWORD, or at the end of a word like this: WORD\\b | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_b)<br>[Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_b2) |
| \\uxxxx       | Find the Unicode character specified by the hexadecimal number xxxx                                    | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_ux)

<br>                                                                         |

| Quantifier | Description                                                      | Try it                                                                      |
| ---------- | ---------------------------------------------------------------- | --------------------------------------------------------------------------- |
| n+         | Matches any string that contains at least one _n_                | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_n1) |
| n\*        | Matches any string that contains zero or more occurrences of _n_ | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_n2) |
| n?         | Matches any string that contains zero or one occurrences of _n_  | [Try it »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_regexp_n3) |
```js
/e/.test("The best things in life are free!"); // true/ false
/e/.exec("The best things in life are free!"); // text/ null
```

### JS Precedence
Expressions in parentheses are computed before the rest of the expression  
Function are executed before the result is used in the rest of the expression   
Postfix increments are executed before prefix increments   
Exponentiations are executed before multiplications   
Multiplications and divisions are executed before additions and subtractions   
Assignments are executed after other operations   
[Details](https://www.w3schools.com/js/js_precedence.asp)

### JS Errors
```js
function myFunction() {
  const message = document.getElementById("p01");
  message.innerHTML = "";
  let x = document.getElementById("demo").value;
  try {
    if(x.trim() == "") throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10) throw "is too high";
    if(x < 5) throw "is too low";
  }
  catch(err) {
    message.innerHTML = "Error: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}

```

### JS Scope
Before ES6 (2015), JavaScript variables had only Global Scope and Function Scope.   
ES6 introduced two important new JavaScript keywords: let and const.   
These two keywords provide Block Scope in JavaScript.   

If you assign a value to a variable that has not been declared, it will automatically become a GLOBAL variable. Do NOT create global variables unless you intend to.
```js
myFunction();

// code here can use carName

function myFunction() {
  carName = "Volvo";
}
```

### JS Hoisting
In JavaScript, a variable can be declared after it has been used.
```js
x = 5; // Assign 5 to x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x;                     // Display x in the element

var x; // Declare x
```
JavaScript only hoists declarations, not initializations.   
To avoid bugs, always declare all variables at the beginning of every scope.
```js
var x = 5; // Initialize x

elem = document.getElementById("demo"); // Find an element
elem.innerHTML = x + " " + y;           // Display x and y

var y = 7; // Initialize y
```

Variables defined with let and const are hoisted to the top of the block, but not initialized.   
Meaning: The block of code is aware of the variable, but it cannot be used until it has been declared.

### JS Strict Mode
```js
"use strict";
x = 3.14;                // Using a variable, without declaring it, is not allowed
x = {p1:10, p2:20};      // Using an object, without declaring it, is not allowed
let x = 3.14;
delete x;                // Deleting a variable (or object) is not allowed
function x(p1, p2) {};
delete x;                // Deleting a function is not allowed
function x(p1, p1) {};   // Duplicating a parameter name is not allowed
let x = 010;             // Octal numeric literals are not allowed
let x = "\010";            // Octal escape characters are not allowed
const obj = {};
Object.defineProperty(obj, "x", {value:0, writable:false});
obj.x = 3.14;  // Writing to a read-only property is not allowed
const obj = {get x() {return 0} };
obj.x = 3.14;            // Writing to a get-only property is not allowed
delete Object.prototype; // Deleting an undeletable property is not allowed
let eval = 3.14;         // The word eval cannot be used as a variable
```

For security reasons, eval() is not allowed to create variables in the scope from which it was called.
```js
"use strict";
eval ("x = 2");
alert (x);      // a variable can not be used before it is declared

eval ("var x = 2");
alert (x);    // eval() can not declare a variable using the var keyword

eval ("let x = 2");
alert (x);        // eval() can not declare a variable using the let keyword
```

The this keyword in functions behaves differently in strict mode.   
The this keyword refers to the object that called the function.   
If the object is not specified, functions in strict mode will return undefined and functions in normal mode will return the global object (window):
```js
"use strict";
function myFunction() {
  alert(this); // will alert "undefined"
}
myFunction();
```
Keywords reserved for future JavaScript versions can NOT be used as variable names in strict mode.

### JS this Keyword
In JavaScript, the this keyword refers to an object.
- In an object method, this refers to the object.
- Alone, this refers to the global object.
- In a function, this refers to the global object.
- In a function, in strict mode, this is undefined.
- In an event, this refers to the element that received the event.
- Methods like call(), apply(), and bind() can refer this to any object.
```js
const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

const person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}

const person2 = {
  firstName:"John",
  lastName: "Doe",
}

// Return "John Doe":
person1.fullName.call(person2); // call() and apply() used to call an object method with another object as argument.

const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName;
  }
}

const member = {
  firstName:"Hege",
  lastName: "Nilsen",
}

let fullName = person.fullName.bind(member); // bind() method, an object can borrow a method from another object
```
### JS Arrow Function
the `this` keyword represents the object that owns the function, no matter who calls the function.
```js
// Regular Function:
hello = function() {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);

// Arrow Function:
hello = () => {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello); // still window
```

### JS Classes
JavaScript Classes are templates for JavaScript Objects.
```js
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age(x) {
    return x - this.year;
  }
}

const date = new Date();
let year = date.getFullYear();

const myCar = new Car("Ford", 2014);
document.getElementById("demo").innerHTML=
"My car is " + myCar.age(year) + " years old.";
```

### JS Modules
```js
export const name = "Jesse";
export const age = 40;

const name = "Jesse";
const age = 40;
export {name, age};

const message = () => {
const name = "Jesse";
const age = 40;
return name + ' is ' + age + 'years old.';
};
export default message; // one default export in a file

import { name, age } from "./person.js"; // named exports
import message from "./message.js"; // default export
```

### JS JSON
```js
let text = '{ "employees" : [' +
'{ "firstName":"John" , "lastName":"Doe" },' +
'{ "firstName":"Anna" , "lastName":"Smith" },' +
'{ "firstName":"Peter" , "lastName":"Jones" } ]}';

const obj = JSON.parse(text); // convert the string into a JavaScript object
```
### JS Debugging
```js
a = 5;
b = 6;
c = a + b;
console.log(c);

let x = 15 * 5;
debugger; // stops the execution of JavaScript, and calls (if available) the debugging function.
document.getElementById("demo").innerHTML = x;
```
### JS Style Guide
```js
firstName = "John"; // camelCase
lastName = "Doe";

price = 19.90; // letter
tax = 0.20;

let x = y + z; // spaces around operators ( = + - * / ), and after commas
const myArray = ["Volvo", "Saab", "Fiat"];

function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32); // 2 spaces for indentation. Different editors interpret tabs differently.
}

const cars = ["Volvo", "Saab", "Fiat"]; // end a simple statement with a semicolon

function toCelsius(fahrenheit) {
  return (5 / 9) * (fahrenheit - 32);
} // Do not end a complex statement with a semicolon.

const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
}; // Always end an object definition with a semicolon.

document.getElementById("demo").innerHTML =
"Hello Dolly."; //  avoid lines longer than 80 characters
```
Hyphens can be mistaken as subtraction attempts. Hyphens are not allowed in JavaScript names. `hyp-hens`, `camelCase`, or `under_scores`
Most web servers (Apache, Unix) are case sensitive about file names. To avoid these problems, always use lower case file names (if possible).

### JS Best Practices
Avoid global variables, avoid `new`, avoid `==` avoid `eval()`   
The eval() function is used to run text as code. In almost all cases, it should not be necessary to use it.

Because it allows arbitrary code to be run, it also represents a security problem.
```js
// All variables used in a function should be declared as local variables.
// Declare at the beginning
let firstName, lastName, price, discount, fullPrice;
// Use later
firstName = "John";
lastName = "Doe";
price = 19.90;
discount = 0.10;
fullPrice = price - discount;

// Declare and initiate at the beginning
let firstName = "";
let lastName = "";
let price = 0;
let discount = 0;
let fullPrice = 0,
const myArray = [];
const myObject = {};

const car = {type:"Fiat", model:"500", color:"white"}; // Declaring objects with const will prevent any accidental change of type

const cars = ["Saab", "Volvo", "BMW"]; // Declaring arrays with const will prevent any accidential change of type:
```
Don't Use new Object()
- Use "" instead of new String()
- Use 0 instead of new Number()
- Use false instead of new Boolean()
- Use {} instead of new Object()
- Use [] instead of new Array()
- Use /()/ instead of new RegExp()
- Use function (){} instead of new Function()
```js
let x1 = "";             // new primitive string
let x2 = 0;              // new primitive number
let x3 = false;          // new primitive boolean
const x4 = {};           // new object
const x5 = [];           // new array object
const x6 = /()/;         // new regexp object
const x7 = function(){}; // new function object
```
Beware of Automatic Type Conversions
```js
let x = "Hello";     // typeof x is a string
x = 5;               // changes typeof x to a number

let x = 5 + 7;       // x.valueOf() is 12,  typeof x is a number
let x = 5 + "7";     // x.valueOf() is 57,  typeof x is a string
let x = "5" + 7;     // x.valueOf() is 57,  typeof x is a string
let x = 5 - 7;       // x.valueOf() is -2,  typeof x is a number
let x = 5 - "7";     // x.valueOf() is -2,  typeof x is a number
let x = "5" - 7;     // x.valueOf() is -2,  typeof x is a number
let x = 5 - "x";     // x.valueOf() is NaN, typeof x is a number
"Hello" - "Dolly"    // does not generate an error but returns NaN (Not a Number)

0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false

function (a=1, b=1) { /*function code*/ } // It is a good habit to assign default values to arguments.

switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
    break;
  default: // Always end your switch statements with a default
    day = "Unknown";
}

// Always treat numbers, strings, or booleans as primitive values. Not as objects.
let x = new String("John");             
let y = new String("John");
(x == y) // is false because you cannot compare objects.
```
### JS Mistakes
```js
let x = 0;
if (x = 10) // Accidentally Using the Assignment Operator

let x = 10;
switch(x) {
  case "10": alert("Hello"); // will not display an alert. switch statements use strict comparison
}

let x = 10;
x = 10 + 5;       // Now x is 15
let y = 10;
y += "5";        // Now y is "105". Confusing Addition & Concatenation

let x = 0.1;
let y = 0.2;
let z = x + y            // the result in z will not be 0.3. Misunderstanding Floats

let z = (x * 10 + y * 10) / 10;       // z will be 0.3

let x = "Hello 
World!"; // errror

let x = "Hello \
World!";

if (x == 19); // misplaced semicolon
{
  // code block 
}

function myFunction(a) {
  let
  power = 10; 
  return // Never break a return statement.
  a * power;
}

person = {firstName:"John", lastName:"Doe", age:46,} // Trailing commas in object and array definition are legal in ECMAScript 5.
points = [40, 100, 1, 5, 25, 10,]; // JSON does not allow trailing commas.
```
In JavaScript, objects use named indexes.   
If you use a named index, when accessing an array, JavaScript will redefine the array to a standard object.   
After the automatic redefinition, array methods and properties will produce undefined or incorrect results   
```js
const person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
person.length;      // person.length will return 0
person[0];          // person[0] will return undefined
```
JavaScript objects, variables, properties, and methods can be undefined.   
In addition, empty JavaScript objects can have the value null.
You cannot test if an object is null, because this will throw an error if the object is undefined.
```js
if (myObj !== null && typeof myObj !== "undefined") // error
if (typeof myObj !== "undefined" && myObj !== null)  // correct
```
### JS Performance
```js
for (let i = 0; i < arr.length; i++) // bad
let l = arr.length; // Statements or assignments that can be placed outside the loop will make the loop run faster.
for (let i = 0; i < l; i++) // better

const obj = document.getElementById("demo"); // If you expect to access a DOM element several times, access it once, and use it as a local variable

// Keep the number of elements in the HTML DOM small.

let fullName = firstName + " " + lastName; // Unnecessary Variables
document.getElementById("demo").innerHTML = fullName;
document.getElementById("demo").innerHTML = firstName + " " + lastName;

//Putting your scripts at the bottom of the page body lets the browser load the page first.
// An alternative is to use defer="true" in the script tag. 
// If possible, you can add your script to the page by code, after the page has loaded
<script>
window.onload = function() {
  const element = document.createElement("script");
  element.src = "myScript.js";
  document.body.appendChild(element);
};
</script>
```
Avoid using the `with` keyword. It has a negative effect on speed. It also clutters up JavaScript scopes.   
The `with` keyword is not allowed in strict mode.
### JS Reserved Words
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