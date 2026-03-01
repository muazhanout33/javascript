# ➡️ Arrow Functions in JavaScript (ES6)

## 🎯 The Third Type of Functions

In addition to Function Declarations and Function Expressions, JavaScript (ES6) introduced a third type:

> **Arrow Functions** — a shorter syntax for writing function expressions.

---

## 1️⃣ Basic Arrow Function

### Function Expression (Old Way)

```javascript
const calcAge2 = function(birthYear) {
  return 2037 - birthYear;
};
```

### Arrow Function (New Way)

```javascript
const calcAge3 = birthYear => 2037 - birthYear;
```

### Usage

```javascript
const age = calcAge3(1991);
console.log(age); // 46
```

### Why is it shorter?

Arrow functions allow:

| | |
|---|---|
| ❌ No `function` keyword | ❌ No `{ }` for single line |
| ❌ No `return` keyword | ✅ Implicit return (automatic) |

---

## ⚡ Implicit Return

If the arrow function has **one expression**, JavaScript returns it automatically.

```javascript
const double = x => x * 2;

double(5); // 10
```

Equivalent to:

```javascript
const double = function(x) {
  return x * 2;
};
```

---

## 2️⃣ Multiple Lines in Arrow Function

If you need more than one line, you **must** use `{ }` and `return`.

```javascript
const yearsUntilRetirement = birthYear => {
  const age = 2037 - birthYear;
  const retirement = 65 - age;
  return retirement;
};

console.log(yearsUntilRetirement(1991)); // 19
```

---

## 3️⃣ Multiple Parameters

If the function has more than one parameter, you **must** wrap them in parentheses `( )`.

```javascript
const yearsUntilRetirement = (birthYear, firstName) => {
  const age = 2037 - birthYear;
  const retirement = 65 - age;
  return `${firstName} retires in ${retirement} years`;
};

console.log(yearsUntilRetirement(1991, "Jonas"));
// Jonas retires in 19 years

console.log(yearsUntilRetirement(1980, "Bob"));
// Bob retires in 8 years
```

---

## ⚖️ Arrow vs Regular Functions

| Feature | Arrow Function | Regular Function |
|---|---|---|
| Syntax | Short | Longer |
| Implicit return | ✅ Yes | ❌ No |
| `this` keyword | ❌ No own `this` | ✅ Has own `this` |
| Best for | Short simple functions | Methods & complex logic |

---

## ⚠️ Important Limitation

Arrow functions do **NOT** have their own `this`.

This makes them:

- ❌ Bad for object methods
- ❌ Bad for constructors
- ✅ Great for small utilities
- ✅ Great for callbacks

> *(You'll learn `this` later in depth.)*

---

## 🏆 When to Use Arrow Functions

✅ One-line calculations  
✅ Array methods (`map`, `filter`, etc.)  
✅ Small helper functions  
✅ Functional programming style  

## 🚫 When NOT to Use Arrow Functions

❌ Object methods  
❌ Constructors  
❌ When you need `this`  
❌ Complex multi-step logic  

---

## 💡 Rule of Thumb

> Use **arrow functions** for small, simple functions  
> Use **regular functions** for everything else
