# 🟢 JavaScript Basics: Values, Variables, and Naming Conventions

## 1️⃣ Values
- Value: The smallest unit of data in programming.  
  Examples: `"Jonas"` (string), `23` (number), `true` (boolean).

```js
console.log("Jonas");
console.log(23);
console.log(true);
Values can also be results of expressions:

console.log(40 + 8 + 23 - 10);
2️⃣ Variables
Variable: A "box" to store a value for reuse.

let firstName = "Jonas";
console.log(firstName);

firstName = "Bob";
console.log(firstName);
3️⃣ Using Variables in console.log
let firstName = "Matilda";
console.log(firstName);
console.log(firstName);
4️⃣ Variable Naming Conventions
Camel Case (Standard in JS)
let firstName;
let myVariable;
Underscore Case (Other languages)
let first_name;
Rules for Variable Names:
// Invalid: cannot start with a number
// let 3name = "Test";

// Valid: letters, numbers, _ or $
let user_1 = "Jonas";
let $price = 100;

// Invalid: reserved keywords
// let new = 27;
5️⃣ Uppercase vs Lowercase in Variable Names
Lowercase for normal variables
let firstName = "Jonas";
Uppercase for Classes
class Person {
  constructor(name) {
    this.name = name;
  }
}

const jonas = new Person("Jonas");
console.log(jonas.name);
Constants in ALL UPPERCASE
const PI = 3.1415;
console.log(PI);
6️⃣ Descriptive Variable Names
let firstJob = "Programmer";
let currentJob = "Teacher";
7️⃣ JavaScript Data Types
String
let name = "Jonas";
console.log(typeof name);
Number
let age = 23;
console.log(typeof age);
Boolean
let isStudent = true;
console.log(typeof isStudent);
Undefined
let job;
console.log(job);
console.log(typeof job);
Null
let empty = null;
console.log(empty);
console.log(typeof empty);
