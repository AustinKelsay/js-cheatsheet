# JavaScript Cheatsheet for Beginners

![](https://bairesdev.mo.cloudinary.net/blog/2023/08/What-Is-JavaScript-Used-For.jpg?tx=w_1920,q_auto)

## Table of Contents
1. [Variable Declaration](#variable-declaration)
2. [Basic Data Types](#basic-data-types)
3. [Operators](#operators)
4. [Objects](#objects)
5. [Functions](#functions)
6. [Arrays](#arrays)
7. [Conditional Statements](#conditional-statements)
8. [Loops](#loops)
9. [Error Handling](#error-handling)
10. [ES6+ Features](#es6-features)
11. [DOM Manipulation](#dom-manipulation)
12. [Event Handling](#event-handling)
13. [Asynchronous JavaScript](#asynchronous-javascript)
14. [Modules](#modules)

## Variable Declaration

In JavaScript, variables can be declared using `var`, `let`, or `const`.

```javascript
var x = 5; // Function-scoped variable (avoid using in modern JavaScript)
let y = 10; // Block-scoped variable
const MAX_POINTS = 100; // Constant (cannot be reassigned)
```

- `var` is function-scoped and hoisted (avoid using in modern JavaScript).
- `let` is block-scoped and can be reassigned.
- `const` is block-scoped and cannot be reassigned (but object properties can be modified).

## Basic Data Types

JavaScript has several basic data types.

```javascript
let num = 42; // Number
let float = 3.14; // Number (JavaScript doesn't distinguish between integers and floats)
let str = "Hello, World!"; // String
let bool = true; // Boolean
let nullValue = null; // Null
let undefinedValue; // Undefined
let symbol = Symbol("unique"); // Symbol (ES6+)
let bigInt = 1234567890123456789012345678901234567890n; // BigInt (ES11+)
```

- `Number`: Represents both integers and floating-point numbers.
- `String`: Represents textual data.
- `Boolean`: Represents `true` or `false`.
- `Null`: Represents a deliberate non-value.
- `Undefined`: Represents a variable that has been declared but not assigned a value.
- `Symbol`: Represents a unique identifier.
- `BigInt`: Represents integers larger than 2^53 - 1.

## Operators
JavaScript includes various types of operators for different operations.

```javascript
// Arithmetic Operators
let sum = 5 + 3;      // Addition: 8
let diff = 10 - 4;    // Subtraction: 6
let product = 3 * 4;  // Multiplication: 12
let quotient = 15 / 3;// Division: 5
let remainder = 17 % 5;// Modulus: 2
let power = 2 ** 3;   // Exponentiation: 8
let increment = 5;
increment++;          // Increment: 6
let decrement = 5;
decrement--;          // Decrement: 4

// Assignment Operators
let x = 10;           // Basic assignment
x += 5;               // Addition assignment (x = x + 5)
x -= 3;               // Subtraction assignment
x *= 2;               // Multiplication assignment
x /= 4;               // Division assignment
x %= 3;               // Modulus assignment
x **= 2;              // Exponentiation assignment

// Comparison Operators
console.log(5 == "5");   // Equal to (with type coercion): true
console.log(5 === "5");  // Strictly equal to: false
console.log(7 != "7");   // Not equal to: false
console.log(7 !== "7");  // Strictly not equal to: true
console.log(10 > 5);     // Greater than: true
console.log(10 >= 10);   // Greater than or equal to: true
console.log(5 < 10);     // Less than: true
console.log(5 <= 5);     // Less than or equal to: true

// Logical Operators
let a = true, b = false;
console.log(a && b);     // Logical AND: false
console.log(a || b);     // Logical OR: true
console.log(!a);         // Logical NOT: false

// Nullish Coalescing Operator (ES2020)
let nullValue = null;
let defaultValue = nullValue ?? "default"; // "default"

// Optional Chaining Operator (ES2020)
let user = {
    address: {
        street: "123 Main St"
    }
};
console.log(user?.address?.street); // "123 Main St"
console.log(user?.contact?.email);  // undefined

// Bitwise Operators
console.log(5 & 3);      // Bitwise AND: 1
console.log(5 | 3);      // Bitwise OR: 7
console.log(5 ^ 3);      // Bitwise XOR: 6
console.log(~5);         // Bitwise NOT: -6
console.log(5 << 1);     // Left shift: 10
console.log(5 >> 1);     // Right shift: 2
console.log(5 >>> 1);    // Unsigned right shift: 2

// String Operators
let str1 = "Hello";
let str2 = "World";
console.log(str1 + " " + str2); // Concatenation: "Hello World"
let greeting = "Hello";
greeting += " World";    // Concatenation assignment

// Type Operators
console.log(typeof "Hello");     // "string"
console.log(typeof 123);         // "number"
console.log(typeof true);        // "boolean"
console.log(obj instanceof Object); // Check if object is instance of a class
```

Key points about operators:
- Arithmetic operators perform mathematical operations
- Assignment operators combine operation with assignment
- Comparison operators return boolean values
- Logical operators work with boolean values and provide short-circuit evaluation
- Nullish coalescing (??) provides a way to specify a default value
- Optional chaining (?.) safely accesses nested object properties
- Bitwise operators perform operations on binary representations
- String operators handle string concatenation
- Type operators help determine variable types

## Objects

Objects are collections of key-value pairs.

```javascript
let person = {
    name: "Alice",
    age: 30,
    sayHello: function() {
        console.log("Hello, my name is " + this.name);
    }
};

// Accessing object properties
console.log(person.name); // Alice
console.log(person["age"]); // 30

// Calling object methods
person.sayHello(); // Hello, my name is Alice

// Adding a new property
person.job = "Developer";

// Object destructuring (ES6+)
let { name, age } = person;
console.log(name, age); // Alice 30
```

- Objects can contain properties and methods.
- Properties can be accessed using dot notation or bracket notation.
- New properties can be added dynamically.
- Object destructuring allows you to extract multiple properties at once.

## Functions

Functions are reusable blocks of code.

```javascript
// Function declaration
function greet(name) {
    return "Hello, " + name + "!";
}

// Function expression
const multiply = function(a, b) {
    return a * b;
};

// Arrow function (ES6+)
const add = (a, b) => a + b;

// Default parameters (ES6+)
function power(base, exponent = 2) {
    return Math.pow(base, exponent);
}

console.log(greet("Alice")); // Hello, Alice!
console.log(multiply(3, 4)); // 12
console.log(add(5, 3)); // 8
console.log(power(3)); // 9
console.log(power(2, 3)); // 8
```

- Functions can be declared using the `function` keyword or as arrow functions.
- Arrow functions provide a more concise syntax and lexically bind `this`.
- Default parameters allow you to specify default values for function arguments.

## Arrays

Arrays are ordered lists of values.

```javascript
let fruits = ["apple", "banana", "orange"];

// Accessing array elements
console.log(fruits[0]); // apple

// Array methods
fruits.push("grape"); // Add to the end
fruits.unshift("mango"); // Add to the beginning
let lastFruit = fruits.pop(); // Remove from the end
let firstFruit = fruits.shift(); // Remove from the beginning

// Iterating over arrays
fruits.forEach(fruit => console.log(fruit));

// Array transformation
let upperFruits = fruits.map(fruit => fruit.toUpperCase());

// Filtering arrays
let longFruits = fruits.filter(fruit => fruit.length > 5);

// Reducing arrays
let totalLength = fruits.reduce((sum, fruit) => sum + fruit.length, 0);

// Spread operator (ES6+)
let moreFruits = ["kiwi", "pear"];
let allFruits = [...fruits, ...moreFruits];
```

- Arrays can contain elements of any type.
- Array methods like `push`, `pop`, `shift`, and `unshift` modify the original array.
- Higher-order functions like `map`, `filter`, and `reduce` create new arrays.
- The spread operator `...` can be used to combine arrays.

## Conditional Statements

Conditional statements allow you to execute code based on certain conditions.

```javascript
let age = 18;

// if...else statement
if (age >= 18) {
    console.log("You are an adult");
} else {
    console.log("You are a minor");
}

// Ternary operator
let status = age >= 18 ? "adult" : "minor";

// switch statement
switch (age) {
    case 13:
        console.log("You're a teenager");
        break;
    case 18:
        console.log("You're now an adult");
        break;
    default:
        console.log("You're neither 13 nor 18");
}
```

- `if...else` statements allow you to execute different code blocks based on conditions.
- The ternary operator provides a concise way to write simple if-else statements.
- `switch` statements are useful when you have multiple conditions to check against a single value.

## Loops

Loops allow you to repeat code multiple times.

```javascript
// for loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// while loop
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}

// do...while loop
let x = 0;
do {
    console.log(x);
    x++;
} while (x < 5);

// for...of loop (ES6+)
let numbers = [1, 2, 3, 4, 5];
for (let num of numbers) {
    console.log(num);
}

// for...in loop (for object properties)
let person = { name: "Alice", age: 30 };
for (let key in person) {
    console.log(key + ": " + person[key]);
}
```

- `for` loops are commonly used when you know how many times you want to iterate.
- `while` loops continue as long as a condition is true.
- `do...while` loops always execute at least once before checking the condition.
- `for...of` loops are used to iterate over iterable objects like arrays.
- `for...in` loops are used to iterate over object properties.

## Error Handling

Error handling allows you to gracefully handle and recover from errors.

```javascript
try {
    // Code that might throw an error
    throw new Error("Something went wrong");
} catch (error) {
    console.error("Caught an error:", error.message);
} finally {
    console.log("This always runs");
}

// Custom error
class CustomError extends Error {
    constructor(message) {
        super(message);
        this.name = "CustomError";
    }
}

try {
    throw new CustomError("A custom error occurred");
} catch (error) {
    if (error instanceof CustomError) {
        console.log("Caught a custom error:", error.message);
    } else {
        console.log("Caught a different error:", error.message);
    }
}
```

- The `try` block contains code that might throw an error.
- The `catch` block handles any errors thrown in the `try` block.
- The `finally` block always executes, regardless of whether an error was thrown.
- You can create custom error types by extending the `Error` class.

## ES6+ Features

ES6 (ECMAScript 2015) and later versions introduced many new features to JavaScript.

```javascript
// Template literals
let name = "Alice";
console.log(`Hello, ${name}!`);

// Destructuring
let [a, b] = [1, 2];
let { x, y } = { x: 3, y: 4 };

// Default parameters
function greet(name = "Guest") {
    console.log(`Hello, ${name}!`);
}

// Rest parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

// Spread operator
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];

// Arrow functions
const square = x => x * x;

// Classes
class Animal {
    constructor(name) {
        this.name = name;
    }
    speak() {
        console.log(`${this.name} makes a sound.`);
    }
}

// Promises
const fetchData = () => {
    return new Promise((resolve, reject) => {
        // Asynchronous operation
        setTimeout(() => resolve("Data fetched"), 1000);
    });
};

// Async/Await
async function getData() {
    try {
        const data = await fetchData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```

- Template literals allow for easy string interpolation.
- Destructuring makes it easy to extract values from arrays or properties from objects.
- Default parameters provide fallback values for function arguments.
- Rest parameters allow functions to accept an indefinite number of arguments as an array.
- The spread operator can be used to expand arrays or objects.
- Arrow functions provide a concise syntax for writing function expressions.
- Classes provide a cleaner syntax for creating objects and implementing inheritance.
- Promises and async/await simplify asynchronous programming.

## DOM Manipulation

DOM manipulation allows you to interact with HTML elements on a web page.

```javascript
// Selecting elements
const element = document.getElementById("myElement");
const elements = document.getElementsByClassName("myClass");
const queryElement = document.querySelector(".myClass");
const queryElements = document.querySelectorAll(".myClass");

// Modifying elements
element.textContent = "New text content";
element.innerHTML = "<strong>New HTML content</strong>";
element.style.color = "red";
element.classList.add("newClass");
element.classList.remove("oldClass");

// Creating and appending elements
const newElement = document.createElement("div");
newElement.textContent = "New element";
document.body.appendChild(newElement);

// Removing elements
element.parentNode.removeChild(element);
// or
element.remove(); // Modern browsers
```

- The DOM (Document Object Model) represents the structure of an HTML document.
- You can select elements using methods like `getElementById`, `getElementsByClassName`, `querySelector`, and `querySelectorAll`.
- Elements can be modified by changing their properties like `textContent`, `innerHTML`, and `style`.
- New elements can be created with `createElement` and added to the DOM with `appendChild`.
- Elements can be removed using `removeChild` or the `remove` method.

## Event Handling

Event handling allows you to respond to user interactions and other events.

```javascript
const button = document.querySelector("#myButton");

// Adding event listeners
button.addEventListener("click", function(event) {
    console.log("Button clicked!");
    console.log("Event object:", event);
});

// Removing event listeners
function handleClick(event) {
    console.log("Button clicked!");
}
button.addEventListener("click", handleClick);
button.removeEventListener("click", handleClick);

// Event delegation
document.body.addEventListener("click", function(event) {
    if (event.target.matches("#myButton")) {
        console.log("Button clicked using event delegation!");
    }
});

// Preventing default behavior
const link = document.querySelector("a");
link.addEventListener("click", function(event) {
    event.preventDefault();
    console.log("Link click prevented");
});
```

- Event listeners can be added to elements using the `addEventListener` method.
- The event object contains information about the event that occurred.
- Event listeners can be removed using `removeEventListener`.
- Event delegation allows you to handle events for multiple elements with a single listener.
- `preventDefault` can be used to stop the default action of an event.

## Asynchronous JavaScript

Asynchronous JavaScript allows you to perform operations without blocking the main thread.

```javascript
// Callbacks
function fetchData(callback) {
    setTimeout(() => {
        callback("Data fetched");
    }, 1000);
}

fetchData(data => console.log(data));

// Promises
function fetchDataPromise() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve("Data fetched");
        }, 1000);
    });
}

fetchDataPromise()
    .then(data => console.log(data))
    .catch(error => console.error(error));

// Async/Await
async function fetchDataAsync() {
    try {
        const data = await fetchDataPromise();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}

fetchDataAsync();

// Fetch API
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```

- Callbacks are functions passed as arguments to be executed later.
- Promises represent the eventual completion or failure of an asynchronous operation.
- Async/await provides a more synchronous-looking way to write asynchronous code.
- The Fetch API is a modern interface for making HTTP requests.

## Modules

Modules allow you to organize your code into reusable pieces.

```javascript
// math.js
export function add(a, b) {
    return a + b;
}

export function multiply(a, b) {
    return a * b;
}

// main.js
import { add, multiply } from './math.js';

console.log(add(5, 3)); // 8
console.log(multiply(4, 2)); // 8

// Default export
// utils.js
export default function sayHello(name) {
    console.log(`Hello, ${name}!`);
}

// main.js
import sayHello from './utils.js';

sayHello("Alice"); // Hello, Alice!
```

- The `export` keyword is used to expose functions, objects, or primitives from a module.
- The `import` keyword is used to bring functionality from other modules into the current module.
- Default exports can be imported without curly braces and can be given any name when importing.

This cheatsheet covers many of the fundamental concepts in JavaScript. Each section provides code examples and explanations to help you understand and use these features effectively in your JavaScript programs.
