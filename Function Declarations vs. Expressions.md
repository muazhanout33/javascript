# ⚙️ Functions in JavaScript: Declarations & Expressions

## 🎯 The Two Main Types

JavaScript has two main ways to write functions:

1. **Function Declarations**
2. **Function Expressions**

Both do almost the same thing, but behave slightly differently.

---

## 1️⃣ Function Declaration

A **Function Declaration** uses the `function` keyword with a name.

### Syntax

```javascript
function calcAge1(birthYear) {
  return 2037 - birthYear;
}
```

### Usage

```javascript
const age1 = calcAge1(1991);
console.log(age1); // 46
```

### Key Points

- `birthYear` → **parameter** (placeholder for input)
- `1991` → **argument** (actual value passed)
- `return` → returns the result
- ✅ Can call the function **before** defining it due to **hoisting**

---

## 2️⃣ Function Expression

A **Function Expression** is a function without a name, stored in a variable.

### Syntax

```javascript
const calcAge2 = function(birthYear) {
  return 2037 - birthYear;
};
```

### Usage

```javascript
const age2 = calcAge2(1991);
console.log(age2); // 46
```

### Key Points

- **Anonymous function** (no name)
- Stored in variable `calcAge2`
- ❌ Cannot call it **before** the definition

---

## ⚖️ Differences Between Declaration & Expression

| Feature | Function Declaration | Function Expression |
|---|---|---|
| Name | Required | Usually anonymous |
| Call before definition | ✅ Yes | ❌ No |
| Use case | General functions | Store functions as values |

> 💡 In JavaScript, functions are **values** just like numbers or strings. You can store them in variables or pass them as arguments.

---

## ✅ Best Practices

- Some developers prefer **function expressions** for cleaner, organized code.
- Others prefer **function declarations** for simplicity.
- The most important thing: **know both** and understand the differences.

---

## 🔎 Example: Age Calculator

### Function Declaration

```javascript
function calcAge1(year) {
  return 2037 - year;
}

console.log(calcAge1(1991)); // 46
```

### Function Expression

```javascript
const calcAge2 = function(year) {
  return 2037 - year;
};

console.log(calcAge2(1991)); // 46
```

> Both produce the **same result**, but the way you call them and define them differs.
