# 🔄 Type Conversion & Type Coercion in JavaScript

## 📚 Introduction

In JavaScript, we have different **data types** like:
- 🔢 **Numbers** (`Number`)
- 📝 **Texts** (`String`)
- ✅ **Boolean values** (`Boolean`)

**Why is type conversion important?**  
Because arithmetic operations and string operations **behave differently** depending on the type.

---

## 🎯 Understanding Data Types

### Example Problem:
```js
let year = "1991";
console.log(year + 18);
```

**What do you expect?**
- 2009? ❌
- "199118"? ✅

**Why?** Because `"1991"` is a **string**, not a number!

---

## 2️⃣ Two Types of Conversion

JavaScript has **two ways** to convert types:

| Type | Who does it? | When? | Example |
|------|-------------|-------|---------|
| **Type Conversion** | You (manually) | When you explicitly tell JS | `Number("23")` |
| **Type Coercion** | JavaScript (automatically) | When JS does it behind the scenes | `"23" - 10` |

---

## 🔧 1. Explicit Conversion (Type Casting)

This is when **you yourself** tell JavaScript to convert a variable from one type to another.

### 🔢 String → Number
```js
let yearString = "1991";
let yearNumber = Number(yearString); // Converts to number

console.log(yearString); // "1991" (string)
console.log(yearNumber); // 1991 (number)
console.log(typeof yearNumber); // "number"
```

---

### Why do we need this?

Without conversion, you get **concatenation** instead of **addition**:
```js
let input = "1991";

// ❌ Wrong (concatenation)
console.log(input + 18); // "199118"

// ✅ Correct (addition)
console.log(Number(input) + 18); // 2009
```

---

### 📝 Number → String
```js
let num = 23;
let str = String(num);

console.log(num); // 23 (number)
console.log(str); // "23" (string)
console.log(typeof str); // "string"
```

---

### 💡 Visual Representation:
```
String "1991"
     ↓
Number("1991")
     ↓
Number 1991
```

---

## ⚡ 2. Automatic Conversion (Type Coercion)

This is when JavaScript **automatically** changes the type of a variable depending on the operation.

### Example 1: Number → String (with + operator)
```js
let age = 23;
let text = "I am " + age; // JS converts 23 to "23"

console.log(text); // "I am 23"
console.log(typeof text); // "string"
```

**What happened?**
```
"I am " + 23
    ↓
"I am " + "23"  (JS converted number to string)
    ↓
"I am 23"
```

---

### Example 2: String → Number (with -, *, / operators)
```js
console.log("23" - 10);  // 13 (not "2310")
console.log("23" * 2);   // 46 (not "2323")
console.log("24" / 2);   // 12
```

**What happened?**
```
"23" - 10
   ↓
23 - 10  (JS converted string to number)
   ↓
13
```

---

### 💡 Important Rule:

| Operator | Behavior | Example | Result |
|----------|----------|---------|--------|
| `+` | Converts to **String** | `"5" + 3` | `"53"` |
| `-` | Converts to **Number** | `"5" - 3` | `2` |
| `*` | Converts to **Number** | `"5" * 3` | `15` |
| `/` | Converts to **Number** | `"6" / 3` | `2` |

---

## 🚨 Converting Non-Numeric Strings

What happens if you try to convert a string that **isn't numeric**?
```js
console.log(Number("Hello")); // NaN
console.log(Number("Jonas")); // NaN
console.log(Number("123abc")); // NaN
```

### What is NaN?

- **NaN** = **N**ot **a** **N**umber
- It means: "This is supposed to be a number, but it's not valid"
- Type of `NaN` is still `"number"` (confusing, right? 😅)
```js
console.log(typeof NaN); // "number"
```

---

### When does NaN appear?
```js
// Invalid conversions
Number("Hello")        // NaN
Number("123abc")       // NaN
Number(undefined)      // NaN

// Invalid math operations
0 / 0                 // NaN
Math.sqrt(-1)         // NaN
```

---

## 📊 Available Type Conversions

JavaScript provides these conversion functions:

| Function | Converts to | Example | Result |
|----------|------------|---------|--------|
| `Number()` | Number | `Number("23")` | `23` |
| `String()` | String | `String(23)` | `"23"` |
| `Boolean()` | Boolean | `Boolean(1)` | `true` |

> **Note:** You generally **cannot** convert anything to `undefined` or `null`

---

## 🎯 Type Conversion Examples

### Example 1: Calculator Input
```js
// User input from form (always a string)
let input1 = "10";
let input2 = "20";

// ❌ Wrong (concatenation)
let wrongSum = input1 + input2;
console.log(wrongSum); // "1020"

// ✅ Correct (addition)
let correctSum = Number(input1) + Number(input2);
console.log(correctSum); // 30
```

---

### Example 2: Age Calculation
```js
let birthYearString = "1991";
let currentYear = 2024;

// Convert to number before calculating
let age = currentYear - Number(birthYearString);
console.log(age); // 33
```

---

### Example 3: Price Calculation
```js
let priceString = "99.99";
let quantity = 3;

// Convert price to number
let total = Number(priceString) * quantity;
console.log(total); // 299.97
```

---

## 🔀 Type Coercion Examples

### Example 1: Mixing Types
```js
// Coercion with +
console.log("I am " + 23 + " years old");
// "I am 23 years old"

// Coercion with -
console.log("23" - "10" - 3);
// 10 (all converted to numbers)

// Mixed operators
console.log("10" - "4" - "3" + 2 + "5");
// Let's break it down:
// "10" - "4" = 6
// 6 - "3" = 3
// 3 + 2 = 5
// 5 + "5" = "55"
```

---

### Example 2: Tricky Cases
```js
// Case 1
console.log(2 + 3 + 4 + "5");
// 9 + "5" = "95"

// Case 2
console.log("10" - "4" - "3" - 2 + "5");
// 10 - 4 = 6
// 6 - 3 = 3
// 3 - 2 = 1
// 1 + "5" = "15"

// Case 3
console.log("5" * "2" + 3);
// 10 + 3 = 13
```

---

## 📋 Quick Summary: Coercion Rules

### Rule 1: + operator
```js
Number + String = String (concatenation)

5 + "5"        // "55"
"Hello" + 5    // "Hello5"
5 + 5 + "5"    // "105" (5+5=10, then "10"+"5"="105")
```

---

### Rule 2: -, *, / operators
```js
String - Number = Number (subtraction)
String * Number = Number (multiplication)
String / Number = Number (division)

"10" - 5       // 5
"10" * 2       // 20
"10" / 2       // 5
```

---

### Rule 3: Order matters with +
```js
// Left to right execution
console.log(5 + 5 + "5");
// 5 + 5 = 10
// 10 + "5" = "105"

console.log("5" + 5 + 5);
// "5" + 5 = "55"
// "55" + 5 = "555"
```

---

## 🎓 Type Conversion vs Type Coercion

### Summary Table:

| Feature | Type Conversion | Type Coercion |
|---------|----------------|---------------|
| **Who does it?** | You (explicit) | JavaScript (implicit) |
| **Control** | Full control | Automatic |
| **Syntax** | `Number()`, `String()` | Happens during operations |
| **Predictability** | Very predictable | Can be surprising |
| **When to use** | Critical calculations | Quick operations |

---

### Visual Comparison:
```js
// TYPE CONVERSION (Explicit)
let year = "1991";
let age = 2024 - Number(year); // You control when conversion happens
console.log(age); // 33

// TYPE COERCION (Implicit)
let text = "The year is " + 2024; // JS automatically converts 2024 to string
console.log(text); // "The year is 2024"
```

---

## 💡 Key Advice

### ✅ Use Explicit Conversion when:
- Doing **precise calculations**
- Working with **user input**
- You want **clear, readable code**
- You need to **avoid bugs**

### ✅ Coercion is OK when:
- Doing **simple operations**
- You **understand the rules**
- The code is **short and obvious**

---

### Best Practice:
```js
// ❌ Relying on coercion (unclear)
let result = birthYear - "10" + age;

// ✅ Explicit conversion (clear)
let result = Number(birthYear) - 10 + Number(age);
```

---

## 📝 Practice Exercises

### Exercise 1: Predict the Output

What will these print?
```js
console.log("5" + 3);
console.log("5" - 3);
console.log("5" * 3);
console.log("5" / 3);
```

<details>
<summary>Click to see answers</summary>
```js
console.log("5" + 3);  // "53" (concatenation)
console.log("5" - 3);  // 2 (subtraction)
console.log("5" * 3);  // 15 (multiplication)
console.log("5" / 3);  // 1.6666... (division)
```

**Why?**
- `+` with string = concatenation
- `-`, `*`, `/` = convert to numbers

</details>

---

### Exercise 2: Fix the Code
```js
let price = "100";
let tax = "15";
let total = price + tax;

console.log(total); // Currently prints "10015" ❌
```

**Fix it to print 115**

<details>
<summary>Click to see answer</summary>
```js
let price = "100";
let tax = "15";
let total = Number(price) + Number(tax);

console.log(total); // 115 ✅
```

</details>

---

### Exercise 3: What's the Output?
```js
console.log(2 + 3 + "7");
console.log("2" + 3 + 7);
```

<details>
<summary>Click to see answer</summary>
```js
console.log(2 + 3 + "7");   // "57"
// 2 + 3 = 5, then 5 + "7" = "57"

console.log("2" + 3 + 7);   // "237"
// "2" + 3 = "23", then "23" + 7 = "237"
```

**Key:** Once there's a string, everything after becomes concatenation!

</details>

---

### Exercise 4: Complex Calculation
```js
let a = "10";
let b = "5";
let c = 2;

// What's the result?
console.log(a - b + c);
```

<details>
<summary>Click to see answer</summary>
```js
console.log(a - b + c); // 7

// Step by step:
// "10" - "5" = 5 (both converted to numbers)
// 5 + 2 = 7
```

</details>

---

### Exercise 5: Tricky One 🔥
```js
console.log("5" + 2 + 3);
console.log(5 + 2 + "3");
```

<details>
<summary>Click to see answer</summary>
```js
console.log("5" + 2 + 3);  // "523"
// "5" + 2 = "52"
// "52" + 3 = "523"

console.log(5 + 2 + "3");  // "73"
// 5 + 2 = 7
// 7 + "3" = "73"
```

**Lesson:** Order matters! Evaluation is left-to-right.

</details>

---

## 🚨 Common Mistakes

### Mistake 1: Forgetting to Convert
```js
// ❌ Wrong
let input = prompt("Enter a number"); // Returns string
let doubled = input * 2;
console.log("Your number doubled: " + doubled);

// ✅ Correct
let input = Number(prompt("Enter a number"));
let doubled = input * 2;
console.log("Your number doubled: " + doubled);
```

---

### Mistake 2: Assuming + Does Math
```js
// ❌ Wrong assumption
let a = "5";
let b = "10";
console.log(a + b); // "510" (not 15!)

// ✅ Correct
console.log(Number(a) + Number(b)); // 15
```

---

### Mistake 3: Not Handling NaN
```js
// ❌ No error checking
let age = Number(userInput);
let nextYear = age + 1; // Could be NaN + 1 = NaN

// ✅ Check for NaN
let age = Number(userInput);
if (isNaN(age)) {
  console.log("Please enter a valid number!");
} else {
  let nextYear = age + 1;
  console.log(nextYear);
}
```

---

## 💎 Pro Tips

### Tip 1: Use Template Literals
```js
// ❌ Harder to read
let message = "User " + name + " is " + age + " years old";

// ✅ Cleaner with template literals
let message = `User ${name} is ${age} years old`;
```

---

### Tip 2: Convert Early
```js
// ❌ Multiple conversions
console.log(Number(a) + Number(b) + Number(c));

// ✅ Convert once
let numA = Number(a);
let numB = Number(b);
let numC = Number(c);
console.log(numA + numB + numC);
```

---

### Tip 3: Use Shorthand
```js
// These are equivalent:
Number("23")    // Explicit
+"23"           // Shorthand (unary + operator)

String(23)      // Explicit
23 + ""         // Shorthand (concatenate with empty string)
```

**Example:**
```js
let year = "1991";

// ✅ Both work:
console.log(Number(year) + 10);  // 2001
console.log(+year + 10);         // 2001
```

---

## 🎯 Real-World Example: Shopping Cart
```js
// User adds items with string prices
let item1 = "49.99";
let item2 = "29.99";
let item3 = "19.99";

// ❌ Wrong calculation
let wrongTotal = item1 + item2 + item3;
console.log(wrongTotal);
// "49.9929.9919.99" ❌

// ✅ Correct calculation
let correctTotal = Number(item1) + Number(item2) + Number(item3);
console.log(correctTotal);
// 99.97 ✅

// Better: Convert to number with parseFloat
let total = parseFloat(item1) + parseFloat(item2) + parseFloat(item3);
console.log(`Total: $${total.toFixed(2)}`);
// "Total: $99.97"
```

---

## 🧠 Key Takeaways

✅ **Type Conversion** = You do it manually (`Number()`, `String()`)  
✅ **Type Coercion** = JavaScript does it automatically  
✅ `+` operator converts to **string** (concatenation)  
✅ `-`, `*`, `/` operators convert to **number**  
✅ `NaN` means "Not a Number" but type is still `number`  
✅ Explicit conversion is **safer** for important calculations  
✅ Understanding coercion helps you write **cleaner code**  
✅ When in doubt, **convert explicitly**

---

## 📊 Conversion Cheat Sheet

### String to Number:
```js
Number("23")         // 23
parseInt("23")       // 23
parseFloat("23.5")   // 23.5
+"23"                // 23 (shorthand)
"23" * 1             // 23 (trick)
```

---

### Number to String:
```js
String(23)           // "23"
(23).toString()      // "23"
23 + ""              // "23" (shorthand)
```

---

### Check if NaN:
```js
isNaN(NaN)           // true
isNaN("hello")       // true (after coercion)
Number.isNaN(NaN)    // true (strict, better)
```

---

## 📚 Resources

- [MDN: Type Conversion](https://developer.mozilla.org/en-US/docs/Glossary/Type_Conversion)
- [MDN: Type Coercion](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion)
- [JavaScript.info: Type Conversions](https://javascript.info/type-conversions)
- [W3Schools: JavaScript Type Conversion](https://www.w3schools.com/js/js_type_conversion.asp)

---

## 🎓 Advanced: typeof Operator

Check the type of any value:
```js
typeof 5              // "number"
typeof "hello"        // "string"
typeof true           // "boolean"
typeof undefined      // "undefined"
typeof null           // "object" (JavaScript bug!)
typeof NaN            // "number" (weird but true!)
```

---

## 🏷️ Tags

`#JavaScript` `#TypeConversion` `#TypeCoercion` `#DataTypes` `#Fundamentals` `#Programming`

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
- Truthy and Falsy values
- Boolean conversion
- Equality operators (`==` vs `===`)
- Logical operators

---

**⭐ If you found this helpful, please star this repo!**

**💬 Have questions? Drop a comment or open an issue!**

**🔗 Share with others learning JavaScript!**
