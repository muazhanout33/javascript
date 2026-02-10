🟢 Declaring Variables in JavaScript
let – const – var

In JavaScript, there are three ways to declare variables:

let

const

var

They are not the same, and each one has a specific use case.

1️⃣ let – Variables That Can Change

Use let when you expect the value to change later.

Example
let age = 30;
age = 31;

console.log(age); // 31


📌 What’s happening:

We declared a variable called age

Then we reassigned its value
This is called reassigning a variable.

Declaring First, Assigning Later
let year;
console.log(year); // undefined

year = 1991;
console.log(year); // 1991


📌 Why do this?

Sometimes you don’t know the value yet

You calculate or assign it later in the code

2️⃣ const – Constant Variables

const means:

A variable that cannot be changed after it is created

Correct Usage
const birthYear = 1991;
console.log(birthYear);

❌ Reassigning const (Error)
const birthYear = 1991;
birthYear = 1990; // ❌ Error


JavaScript will throw:

TypeError: Assignment to constant variable

❌ const Without a Value (Error)
const job;


Error:

Missing initializer in const declaration

📌 Rule:

const must have a value when declared

🧠 let vs const – Best Practice
✅ Best Practice Rule

Always use const by default
Use let only if the value will change

Example
const birthYear = 1991; // never changes
let age = 30;           // changes over time


📌 Benefits:

Fewer bugs

Cleaner code

Easier to understand

3️⃣ var – The Old Way (Avoid ❌)

Before ES6, JavaScript used var.

var job = "Programmer";
job = "Teacher";

console.log(job);


⚠️ This works, but it’s not recommended.

Why NOT use var?

Confusing scope rules

Causes hard-to-track bugs

Outdated compared to let and const

📌 Modern JavaScript rule:

❌ Don’t use var

4️⃣ Declaring Variables Without Keywords (Very Bad 🚨)
lastName = "Schmedtmann";
console.log(lastName);


📌 This works, but:

Creates a global variable

Can break large applications

Very dangerous practice

Golden Rule 🏆

Always declare variables using let or const

📊 Quick Comparison
Keyword	Reassignable	Can Be Empty	Recommended
let	✅ Yes	✅ Yes	When value changes
const	❌ No	❌ No	Default choice
var	✅ Yes	✅ Yes	❌ Avoid
🔚 Summary

✔️ Use const by default

✔️ Use let if the value will change

❌ Never use var

❌ Never declare variables without keywords
