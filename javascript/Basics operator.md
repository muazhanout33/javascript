In this lesson, we learn JavaScript operators, which are one of the most important basics in the language.

What is an Operator?

An operator allows us to:

Transform values

Combine multiple values

Perform actions on values (calculations, comparisons, assignments, etc.)

JavaScript has many types of operators, such as:

Arithmetic Operators

Assignment Operators

Comparison Operators

Logical Operators (we’ll learn later)

In this lesson, we focus on the main basic ones.

1️⃣ Arithmetic Operators

Arithmetic operators are used to perform math operations.

Common Arithmetic Operators
Operator	Meaning
+	Addition
-	Subtraction
*	Multiplication
/	Division
**	Exponentiation (power)
Example: Calculating Age
```js
const ageJonas = 2037 - 1991;
console.log(ageJonas); // 46
```

Here:

- is the subtraction operator

We calculate Jonas’s age

Another Person
```js
const ageSarah = 2037 - 2018;
console.log(ageSarah); // 19
```
Logging Multiple Values

You can log more than one value at the same time:
```js
console.log(ageJonas, ageSarah);
```

Output:

46 19

Why Variables Are Important (Avoid Repetition)

Bad practice ❌ (repeating values):

const ageJonas = 2037 - 1991;
const ageSarah = 2037 - 2018;


Good practice ✅ (use variables):
```js
const now = 2037;

const ageJonas = now - 1991;
const ageSarah = now - 2018;

```
✅ If the year changes, we only change it once.

More Arithmetic Examples
```js
console.log(ageJonas * 2);   // 92
console.log(ageJonas / 10);  // 4.6
console.log(2 ** 3);         // 8
```
Explanation:

2 ** 3 means:
2 × 2 × 2 = 8

2️⃣ The + Operator with Strings (Concatenation)

The + operator is also used to join strings.
```js
const firstName = "Jonas";
const lastName = "Schmedtmann";

console.log(firstName + lastName);
```

Output:
```js
JonasSchmedtmann

Adding Space Between Strings
console.log(firstName + " " + lastName);

```
Output:

Jonas Schmedtmann


📌 This is called string concatenation.

(There is a better way using template literals, but later 😉)

3️⃣ Assignment Operators

Assignment operators assign values to variables.

Basic Assignment
let x = 10 + 5; // 15


Here:

+ runs first

Then = assigns the result to x

More Assignment Operators
x += 10; // x = x + 10 → 25
x *= 4;  // x = x * 4 → 100
x++;     // x = x + 1 → 101
x--;     // x = x - 1 → 100


📌 These operators modify the variable’s value.

4️⃣ Comparison Operators

Comparison operators return Boolean values:

true

false

Common Comparison Operators
Operator	Meaning
>	Greater than
<	Less than
>=	Greater than or equal
<=	Less than or equal
Example: Comparing Ages
console.log(ageJonas > ageSarah);


Output:

true


Because:

Jonas is 46

Sarah is 19

Real Example: Full Age Check
const fullAge = ageSarah >= 18;
console.log(fullAge);


If Sarah is 18 or older → true

If younger → false

Why >= and not >?

Because:

>= 18 includes exactly 18

Legal age usually means 18 or more

5️⃣ Storing Comparison Results

Instead of logging directly, we usually store results:

const isAdult = ageSarah >= 18;


📌 This variable will always be a Boolean.

6️⃣ Doing Everything in One Line

Instead of calculating ages separately:

console.log((2037 - 1991) > (2037 - 2018));


This works because JavaScript knows:

Do arithmetic first

Then do comparison

This is called operator precedence
👉 and it’s the topic of the next lesson.

✅ Summary

Operators perform actions on values

Arithmetic operators → math

+ joins strings

Assignment operators update variables

Comparison operators return true or false

JavaScript knows which operator runs first

# ⚙️ Operator Precedence in JavaScript

## 📚 What is Operator Precedence?

**Operator Precedence** means:
> The order in which JavaScript executes operators when there's more than one in a single expression.

**In simple words:**
When you have multiple operators in one line, which one runs first?

---

## 🎯 Why Is Operator Precedence Important?

### Example:
```js
2037 - 1991 > 2037 - 2018
```

This returns `true` ✅

**But why does JavaScript do subtraction first, then comparison?**

👉 **Answer:** Operator Precedence Rules

---

## 📊 Operator Precedence Table (MDN)

JavaScript has a **well-defined precedence order**.

The best reference: [MDN Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

The table shows:
- ✅ Which operators run first
- ✅ Which run later
- ✅ Which run left-to-right
- ✅ Which run right-to-left

> 📌 **Note:** You do NOT need to memorize the numbers!  
> Just understand the **general idea**.

---

## 🔑 Key Rule to Remember

### ✅ Arithmetic operators run **BEFORE** comparison operators

**Example:**
```js
2037 - 1991 > 2037 - 2018
```

**Execution order:**

1. `2037 - 1991` → `46`
2. `2037 - 2018` → `19`
3. `46 > 19` → `true`

---

## ⬅️➡️ Left-to-Right vs Right-to-Left

Some operators execute:
- **Left to Right** (most operators)
- **Right to Left** (assignment, exponentiation)

---

### Example: Left-to-Right (Subtraction)
```js
console.log(25 - 10 - 5);
```

**Execution:**
```
25 - 10 = 15
15 - 5 = 10
```

**Output:**
```
10
```

✔️ Subtraction runs **left to right**

---

## 🔄 Assignment Operators Run Right-to-Left

Assignment (`=`) is **very special** — it runs **right to left**.

### Example:
```js
let x, y;

x = y = 25 - 10 - 5;

console.log(x, y);
```

**Output:**
```
10 10
```

---

### Why does this happen?

**Step by step:**

**1️⃣ Arithmetic first:**
```js
25 - 10 - 5 = 10
```

Now the code becomes:
```js
x = y = 10;
```

**2️⃣ Assignment runs right-to-left:**

- `y = 10` (first)
- `x = y` (then x becomes 10)

So:
```js
x = 10
y = 10
```

✅ That's why both are `10`

---

### ❌ Why NOT Left-to-Right?

If assignment worked **left to right**:
```js
x = y;  // y is undefined ❌
y = 10;
```

❌ **Wrong result!**

So **right-to-left** assignment makes sense ✅

---

## 🎯 Parentheses Have the Highest Precedence

Just like math in school 🏫  
**Anything inside parentheses runs first!**

---

### Example: Calculating Average Age (❌ WRONG Way)
```js
const ageJonas = 46;
const ageSarah = 19;

const averageAge = ageJonas + ageSarah / 2;
console.log(averageAge);
```

**Output:**
```
55.5
```

❌ **WRONG!**  
How can the average be bigger than 46?

---

### Why did this happen?

Because:
- Division `/` runs **before** addition `+`

So JavaScript does:
```js
ageSarah / 2 = 9.5
46 + 9.5 = 55.5
```

---

### ✅ Correct Way (Using Parentheses)
```js
const averageAge = (ageJonas + ageSarah) / 2;
console.log(averageAge);
```

**Output:**
```
32.5
```

✔️ **CORRECT!**

---

### Why?

Because:
- **Parentheses force addition first**
- Then division happens
```js
(46 + 19) / 2
= 65 / 2
= 32.5
```

---

## 📋 Summary Table

| Operator Type | Example | Execution Order | Direction |
|---------------|---------|-----------------|-----------|
| Parentheses | `(a + b)` | Highest priority | N/A |
| Exponentiation | `a ** b` | High | Right-to-Left |
| Multiplication/Division | `a * b`, `a / b` | Medium | Left-to-Right |
| Addition/Subtraction | `a + b`, `a - b` | Medium | Left-to-Right |
| Comparison | `a > b`, `a < b` | Low | Left-to-Right |
| Assignment | `a = b` | Lowest | Right-to-Left |

---

## 🧠 Final Summary

✅ JavaScript follows **operator precedence rules**  
✅ **Arithmetic** → runs before **comparison**  
✅ **Assignment** (`=`) → runs **right-to-left**  
✅ Most **math operators** → run **left-to-right**  
✅ **Parentheses** `()` → **always highest priority**  
✅ **When in doubt** → use parentheses!

---

## 💡 Pro Tip

> Even if you know precedence rules:  
> **Always use parentheses to make code clearer!**

**Readable code = Fewer bugs** ✅

---

## 📚 Resources

- [MDN: Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
- [JavaScript.info: Operators](https://javascript.info/operators)

---

## 📝 Practice Examples

### Exercise 1:
```js
console.log(10 + 5 * 2);
```

**What's the output?**

<details>
<summary>Click to see answer</summary>
```
20
```

**Why?** Multiplication runs before addition:
- `5 * 2 = 10`
- `10 + 10 = 20`

</details>

---

### Exercise 2:
```js
let a = 5;
let b = 10;
let c = a = b + 5;

console.log(a, b, c);
```

**What's the output?**

<details>
<summary>Click to see answer</summary>
```
15 10 15
```

**Why?** Assignment runs right-to-left:
- `b + 5 = 15`
- `a = 15`
- `c = 15`

</details>

---

### Exercise 3:
```js
console.log(20 - 10 - 5);
console.log(20 - (10 - 5));
```


