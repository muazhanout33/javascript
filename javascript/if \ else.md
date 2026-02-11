# 🎯 Making Decisions in JavaScript (if / else)

## 📚 Introduction

Now we want to make our programs **more realistic** by allowing them to **make decisions**.

**Real-world scenario:**
> Check if a person is allowed to start a driving license.  
> - If **yes** → print a message  
> - If **not** → print how many years are left

---

## ✅ Step 1: Basic if Statement

### Example:
```js
let age = 19;

if (age >= 18) {
  console.log("You can start your driving license 🚗");
}
```

### 🔎 How this works:

1. `age >= 18` is a **condition**
2. It returns either:
   - `true` ✅
   - `false` ❌
3. If it's `true`, the code inside `{}` runs
4. If it's `false`, nothing happens

---

### Try changing the age:
```js
let age = 15;

if (age >= 18) {
  console.log("You can start your driving license 🚗");
}
```

**Output:**
```
(nothing prints)
```

❌ Nothing happens because the condition is `false`

---

## ✅ Adding else Block

If we want something to happen when the condition is **false**, we use `else`.

### Example:
```js
let age = 15;

if (age >= 18) {
  console.log("You can start your driving license 🚗");
} else {
  let yearsLeft = 18 - age;
  console.log(`You are too young. Wait ${yearsLeft} more years.`);
}
```

### 🔥 What happens here?

- If `age >= 18` → **first block** runs
- Otherwise → **second block** runs

**Output (when age = 15):**
```
You are too young. Wait 3 more years.
```

---

## 🎮 How if/else Works (Flow Chart)
```
START
  ↓
[Condition?]
  ↓         ↓
 true      false
  ↓         ↓
[if block] [else block]
  ↓         ↓
  └────┬────┘
       ↓
     END
```

---

## 📌 Important Concept: Control Structure

`if / else` is called a **Control Structure**

**Why?**  
Because it **controls** which code runs and which code does not.

### Without Control Structure:
```js
// JavaScript runs code line by line
console.log("Line 1");
console.log("Line 2");
console.log("Line 3");
// All 3 lines ALWAYS run
```

### With Control Structure:
```js
if (condition) {
  console.log("This runs only if condition is true");
} else {
  console.log("This runs only if condition is false");
}
// Only ONE block runs, not both!
```

---

## 🎯 Second Example: Finding the Century

Let's build a small logic example.

**Goal:**  
Determine the century based on birth year.

**Rules:**
- Birth year ≤ 2000 → 20th century
- Birth year > 2000 → 21st century

---

### ❌ Wrong Way (will cause error)
```js
let birthYear = 1998;

if (birthYear <= 2000) {
  let century = 20;
} else {
  let century = 21;
}

console.log(century); // ❌ ReferenceError: century is not defined
```

---

### 🚫 Why Error?

Because variables declared inside `{}` are **block-scoped** (with `let`).

They **cannot be accessed** outside the block.

**Visual representation:**
```js
if (condition) {
  let century = 20; // ← Exists only INSIDE this block
}
// century does NOT exist here ❌

console.log(century); // Error!
```

---

### ✅ Correct Way

**Solution:** Declare the variable **outside** the block first:
```js
let birthYear = 1998;
let century; // ← Declared outside

if (birthYear <= 2000) {
  century = 20; // ← Assign value (not declare)
} else {
  century = 21; // ← Assign value (not declare)
}

console.log(century); // ✅ 20
```

---

### Try another year:
```js
let birthYear = 2012;
let century;

if (birthYear <= 2000) {
  century = 20;
} else {
  century = 21;
}

console.log(century); // ✅ 21
```

---

## 📊 Comparison: let Inside vs Outside

| Declaration Location | Inside if/else | Outside if/else |
|---------------------|----------------|-----------------|
| **Scope** | Block-scoped | Function/global scoped |
| **Accessible outside?** | ❌ No | ✅ Yes |
| **Use case** | Temporary variables | Variables you need later |

### Example:
```js
// ❌ WRONG
if (true) {
  let temp = 10;
}
console.log(temp); // Error

// ✅ CORRECT
let temp;
if (true) {
  temp = 10;
}
console.log(temp); // 10
```

---

## 📌 if/else Syntax Summary

### Basic Structure:
```js
if (condition) {
  // runs if condition is TRUE
} else {
  // runs if condition is FALSE
}
```

### Important Rules:

1. **Condition** must return `true` or `false`
2. Only **ONE block** runs (either if OR else, never both)
3. `else` is **optional** (you can have just `if`)
4. Variables declared with `let/const` inside blocks are **block-scoped**

---

## 🎯 Common Conditions

### Comparison Operators:

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `>` | Greater than | `5 > 3` | `true` |
| `<` | Less than | `5 < 3` | `false` |
| `>=` | Greater or equal | `5 >= 5` | `true` |
| `<=` | Less or equal | `5 <= 3` | `false` |
| `===` | Equal (strict) | `5 === 5` | `true` |
| `!==` | Not equal (strict) | `5 !== 3` | `true` |

### Example:
```js
let age = 18;

if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

---

## 🚀 Why This Is Important

Decision making is **one of the most important things** in programming.

You use it for:
- ✅ **Login systems** (check password)
- ✅ **Form validation** (check if email is valid)
- ✅ **Game logic** (check if player won)
- ✅ **AI decisions** (choose next action)
- ✅ **Business rules** (apply discount?)
- ✅ **Automation systems** (like N8N workflows 🔥)

---

## 📝 Practice Examples

### Exercise 1: Age Check
```js
let age = 16;

// Write if/else to check:
// if age >= 18 → "You can vote"
// else → "Too young to vote"
```

<details>
<summary>Click to see answer</summary>
```js
let age = 16;

if (age >= 18) {
  console.log("You can vote");
} else {
  console.log("Too young to vote");
}
```

**Output:**
```
Too young to vote
```

</details>

---

### Exercise 2: Grade Check
```js
let score = 85;

// Write if/else to check:
// if score >= 50 → "Pass"
// else → "Fail"
```

<details>
<summary>Click to see answer</summary>
```js
let score = 85;

if (score >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

**Output:**
```
Pass
```

</details>

---

### Exercise 3: Temperature Check
```js
let temperature = 30;

// Write if/else to check:
// if temperature > 25 → "It's hot"
// else → "It's cold"
```

<details>
<summary>Click to see answer</summary>
```js
let temperature = 30;

if (temperature > 25) {
  console.log("It's hot");
} else {
  console.log("It's cold");
}
```

**Output:**
```
It's hot
```

</details>

---

### Exercise 4: Variable Scope Challenge ⚡

**What's wrong with this code?**
```js
if (true) {
  let message = "Hello";
}

console.log(message);
```

<details>
<summary>Click to see answer</summary>

**Error:** `ReferenceError: message is not defined`

**Why?**  
`message` is declared inside the if block, so it's not accessible outside.

**Fix:**
```js
let message;

if (true) {
  message = "Hello";
}

console.log(message); // ✅ "Hello"
```

</details>

---

### Exercise 5: Century Calculator
```js
let birthYear = 2005;

// Write code to determine the century
// birthYear <= 2000 → "20th century"
// birthYear > 2000 → "21st century"
```

<details>
<summary>Click to see answer</summary>
```js
let birthYear = 2005;
let century;

if (birthYear <= 2000) {
  century = "20th century";
} else {
  century = "21st century";
}

console.log(century); // ✅ "21st century"
```

</details>

---

## 🎓 Advanced: What if we have more than 2 options?

Use `else if`:
```js
let score = 85;

if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 80) {
  console.log("Grade: B");
} else if (score >= 70) {
  console.log("Grade: C");
} else {
  console.log("Grade: F");
}
```

**Output:**
```
Grade: B
```

> **Note:** We'll learn more about `else if` in the next lesson!

---

## 🧠 Key Takeaways

✅ `if` statement executes code **only if condition is true**  
✅ `else` statement executes code **if condition is false**  
✅ **Only ONE block** runs (if OR else, never both)  
✅ Conditions must evaluate to `true` or `false`  
✅ Variables declared with `let/const` inside blocks are **block-scoped**  
✅ Declare variables **outside** if you need them later  
✅ `if/else` is a **Control Structure** that controls program flow

---

## 💡 Pro Tips

### Tip 1: Use meaningful variable names
```js
// ❌ Bad
if (a > b) {
  c = 20;
}

// ✅ Good
if (birthYear <= 2000) {
  century = 20;
}
```

---

### Tip 2: Always use curly braces {}

Even if you have one line:
```js
// ❌ Works but not recommended
if (age >= 18)
  console.log("Adult");

// ✅ Better (more readable)
if (age >= 18) {
  console.log("Adult");
}
```

---

### Tip 3: Keep conditions simple
```js
// ❌ Hard to read
if (((age >= 18) && (hasLicense === true)) || (isAdult)) {
  // ...
}

// ✅ Better
let canDrive = (age >= 18 && hasLicense) || isAdult;

if (canDrive) {
  // ...
}
```

---

## 📚 Resources

- [MDN: if...else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
- [JavaScript.info: Conditional operators](https://javascript.info/ifelse)
- [W3Schools: JavaScript if else](https://www.w3schools.com/js/js_if_else.asp)

---

## 🎯 Challenge: Build a Simple Program

Create a program that:
1. Takes a person's age
2. Checks if they can:
   - Drive (age >= 18)
   - Vote (age >= 18)
   - Drink alcohol (age >= 21)
3. Prints appropriate messages

<details>
<summary>Click to see solution</summary>
```js
let age = 20;
let message = "";

// Check driving
if (age >= 18) {
  message += "✅ You can drive\n";
} else {
  message += "❌ You cannot drive\n";
}

// Check voting
if (age >= 18) {
  message += "✅ You can vote\n";
} else {
  message += "❌ You cannot vote\n";
}

// Check drinking
if (age >= 21) {
  message += "✅ You can drink alcohol\n";
} else {
  message += "❌ You cannot drink alcohol\n";
}

console.log(message);
```

**Output (age = 20):**
```
✅ You can drive
✅ You can vote
❌ You cannot drink alcohol
```

</details>

---

## 🏷️ Tags

`#JavaScript` `#IfElse` `#Conditionals` `#ControlStructures` `#Programming` `#Fundamentals`

---

## 👤 Author

[Your Name]  
📧 [your@email.com]  
🔗 [GitHub](https://github.com/yourusername)

---

## 📜 License

MIT License - Feel free to use and share!

---

## 🔜 What's Next?

In the next lesson, we'll learn about:
- `else if` statements
- Multiple conditions
- Nested if statements
- Ternary operator (`? :`)

---

**⭐ If you found this helpful, please star this repo!**

**📌 Have questions? Open an issue or discussion!**
