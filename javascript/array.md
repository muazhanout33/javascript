# 📦 Arrays in JavaScript

## 1️⃣ Why Arrays?

- Arrays are **data structures** that let you store multiple values in one container.
- Without arrays, if you had 10 friends, you'd need 10 separate variables — which is annoying.
- Instead, you can put all your friends in **one array** and access them by index.

---

## 2️⃣ Creating Arrays

### Option 1 — Literal Syntax *(most common)*

```javascript
const friends = ["Michael", "Steven", "Peter"];
```

- Each value is separated by a comma.
- Strings must be wrapped in quotes `" "`.
- `friends[0]` → `"Michael"` *(arrays are zero-indexed)*
- `friends[1]` → `"Steven"`
- `friends[2]` → `"Peter"`

### Option 2 — Using `new Array()`

```javascript
const years = new Array(1991, 1984, 2008, 2020);
```

- Works with numbers, strings, or any type.
- Less common than the literal syntax.

---

## 3️⃣ Accessing Elements

Use **square brackets** with the index:

```javascript
console.log(friends[0]); // Michael
console.log(friends[2]); // Peter
```

Access the **last element** dynamically:

```javascript
console.log(friends[friends.length - 1]); // Peter
```

> `length` gives the **total number of elements**, not the last index.

---

## 4️⃣ Changing Elements

Even if an array is declared with `const`, you can **modify its contents**:

```javascript
friends[2] = "Jay"; // Replace Peter with Jay
console.log(friends); // ["Michael", "Steven", "Jay"]
```

But you **cannot reassign** the whole array if it's `const`:

```javascript
friends = ["Bob", "Alice"]; // ❌ ERROR
```

---

## 5️⃣ Arrays Can Store Different Types

```javascript
const jonas = ["Jonas", "Schmedtmann", 2037 - 1991, "teacher", friends];
```

- Mixed data types are perfectly fine.
- You can even store **arrays inside arrays**.

---

## 6️⃣ Using Functions Inside Arrays

Suppose you have a function `calcAge(year)`:

```javascript
const years = [1990, 1967, 2002, 2010, 2018];

const ages = [
  calcAge(years[0]),
  calcAge(years[1]),
  calcAge(years[years.length - 1])
];

console.log(ages);
```

- You can call functions for individual elements and store the results in a new array.
- This works because arrays can store **any value returned by an expression or function**.

---

## ✅ Key Takeaways

| # | Concept |
|---|---|
| 1 | Arrays group multiple values in one container |
| 2 | Access elements by index, starting from `0` |
| 3 | Use `.length` to get the number of elements |
| 4 | You can change elements in a `const` array, but cannot replace the whole array |
| 5 | Arrays can store any type — numbers, strings, or even other arrays |
| 6 | You can use functions to generate values and store them in arrays |
