# 🔄 Truthy & Falsy Values in JavaScript

## 📚 Introduction

In JavaScript, **every value can be converted to a Boolean** in logical contexts like `if`, `while`, or logical operators (`&&`, `||`).  

- **Falsy values** → become `false`  
- **Truthy values** → become `true`

Understanding this helps you write **cleaner and safer code**.

---

## ⚡ 1️⃣ Falsy Values

Only **5 values** are falsy:

```js
0          // zero
""         // empty string
undefined  // undefined
null       // null
NaN        // Not a Number

console.log(Boolean(0));         // false
console.log(Boolean(""));        // false
console.log(Boolean(undefined)); // false
console.log(Boolean(null));      // false
console.log(Boolean(NaN));       // false
console.log(Boolean(23));        // true
console.log(Boolean("Hello"));   // true
console.log(Boolean({}));        // true (empty object)
console.log(Boolean([]));        // true (empty array)

let money = 0;

if (money) {
  console.log("Don't spend it all!");
} else {
  console.log("You have no money 😢");
}
// Output: "You have no money 😢"

money = 100;

if (money) {
  console.log("Don't spend it all!");
} else {
  console.log("You have no money 😢");
}
// Output: "Don't spend it all!"


📝 4️⃣ Checking if a Variable is Defined
let height;

if (height) {
  console.log("Height is set!");
} else {
  console.log("Height is undefined or falsy");
}
// Output: "Height is undefined or falsy"


Be careful: 0 is falsy, even though it's a valid number:

height = 0;

if (height) {
  console.log("Height is set!");
} else {
  console.log("Height is undefined or falsy");
}
// Output: "Height is undefined or falsy" ❌

💡 Summary
Type	Example	Boolean Conversion
Falsy	0, "", undefined, null, NaN	false
Truthy	23, "Hello", {}, []	true
🔀 Real-Life Examples
Example 1: Money Check
let money = 0;

if (money) {
  console.log("Don't spend it all!");
} else {
  console.log("You have no money 😢");
}

Example 2: Checking User Input
let height;

if (height) {
  console.log(`Height is ${height}`);
} else {
  console.log("Height is not defined");
}

⚠️ Gotchas

0 is falsy, but might be a valid number

"" is falsy, but sometimes it's meaningful input

null and undefined are falsy → good for checking "not set"

📊 Quick Tips

Use Boolean() for explicit conversion

let value = "Hello";
console.log(Boolean(value)); // true


Falsy check shortcut

if (!value) {
  console.log("Value is falsy");
}


Truthy check

if (value) {
  console.log("Value is truthy");
}
