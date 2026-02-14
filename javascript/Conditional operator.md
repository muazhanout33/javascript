# ❓ Conditional (Ternary) Operator in JavaScript

## 📚 Introduction

The **Ternary Operator** is a **shortcut** for writing simple `if-else` statements in **one line**.

**Think of it as:**
> A compact way to make quick decisions and assign values

---

## 🎯 What is the Ternary Operator?

It's a **conditional operator** that takes **three operands**:
```js
condition ? valueIfTrue : valueIfFalse
```

### Basic Example:
```js
const age = 23;

const drink = age >= 18 ? "wine" : "water";

console.log(drink); // "wine"
```

**How it works:**
- If `age >= 18` is `true` → return `"wine"`
- If `age >= 18` is `false` → return `"water"`

---

## 🔄 Ternary vs if-else

### Using Ternary (1 line):
```js
const age = 23;
const drink = age >= 18 ? "wine" : "water";
```

---

### Same Logic with if-else (7 lines):
```js
const age = 23;
let drink;

if (age >= 18) {
  drink = "wine";
} else {
  drink = "water";
}
```

**Ternary = Shorter + Cleaner!** ✅

---

## 📐 Understanding the Syntax

### Three Parts (that's why it's called "ternary"):
```js
condition ? valueIfTrue : valueIfFalse
    1           2             3
```

### Visual Breakdown:
```js
age >= 18  ?  "wine"  :  "water"
    │          │          │
 condition   if true   if false
```

---

### Example with Labels:
```js
const isAdult = age >= 18 ? true : false;
//              ─┬─ ─┬─  ─┬─   ─┬─  ─┬─
//               │   │    │     │    │
//            condition  │   value  value
//                      ternary  if     if
//                      operator true  false
```

---

## ⭐ Key Concept: Ternary is an Expression

### 🔑 Most Important Difference:

**if-else** = **Statement** (does something)  
**Ternary** = **Expression** (produces a value)

### What does this mean?

✅ **You can use ternary anywhere you need a value:**

1. **Assign to variable:**
```js
   const message = age >= 18 ? "Adult" : "Minor";
```

2. **Inside template literals:**
```js
   console.log(`You are ${age >= 18 ? "an adult" : "a minor"}`);
```

3. **Return from function:**
```js
   return age >= 18 ? "wine" : "water";
```

4. **As function argument:**
```js
   console.log(age >= 18 ? "wine" : "water");
```

5. **In array:**
```js
   const items = [name, age >= 18 ? "adult" : "minor"];
```

---

### ❌ You CANNOT do this with if-else:
```js
// ❌ Syntax Error!
const drink = if (age >= 18) { "wine" } else { "water" };
```

**Why?** `if-else` is a **statement**, not an expression.

---

## 💬 Using Ternary in Template Literals

This is where ternary **really shines**! ✨

### Example 1: Simple Message
```js
const age = 23;

console.log(`I like to drink ${age >= 18 ? "wine 🍷" : "water 💧"}`);
```

**Output:**
```
I like to drink wine 🍷
```

---

### Example 2: Greeting
```js
const hour = 14;

console.log(`Good ${hour < 12 ? "morning" : "afternoon"}!`);
```

**Output:**
```
Good afternoon!
```

---

### Example 3: Multiple Ternaries
```js
const temperature = 30;

console.log(`It's ${temperature > 25 ? "hot 🔥" : temperature > 15 ? "warm ☀️" : "cold ❄️"}`);
```

**Output:**
```
It's hot 🔥
```

**Note:** Nested ternaries can get confusing! Use carefully.

---

### ❌ Impossible with if-else:
```js
// ❌ Can't do this!
console.log(`Message: ${if (age >= 18) { "adult" } else { "minor" }}`);

// ✅ Have to do this (less clean):
let status;
if (age >= 18) {
  status = "adult";
} else {
  status = "minor";
}
console.log(`Message: ${status}`);
```

---

## 📊 Ternary vs if-else Comparison

| Feature | Ternary | if-else |
|---------|---------|---------|
| **Type** | Expression | Statement |
| **Returns value** | ✅ Yes | ❌ No |
| **Lines of code** | 1 line | Multiple lines |
| **Use in template literals** | ✅ Yes | ❌ No |
| **Assign to variable** | ✅ Direct | Need extra step |
| **Complex logic** | ❌ Gets messy | ✅ Better |
| **Multiple statements** | ❌ No | ✅ Yes |
| **Readability** | ✅ Good for simple | ✅ Good for complex |

---

## ✅ When to Use Ternary

### ✅ Perfect for:

1. **Simple conditions** (one line logic)
2. **Assigning values** based on condition
3. **Inside template strings**
4. **Returning from functions**
5. **Quick true/false checks**

### Example - Good Use Cases:
```js
// ✅ Assigning value
const status = isLoggedIn ? "online" : "offline";

// ✅ In template literal
console.log(`User is ${isActive ? "active" : "inactive"}`);

// ✅ Function return
const getGreeting = (hour) => hour < 12 ? "Good morning" : "Good evening";

// ✅ Setting CSS class
const className = isValid ? "success" : "error";

// ✅ Conditional rendering (React)
return <div>{isLoading ? <Spinner /> : <Content />}</div>;
```

---

## 🚫 When NOT to Use Ternary

### ❌ Avoid for:

1. **Multiple statements** in each branch
2. **Complex logic**
3. **Nested ternaries** (hard to read)
4. **When readability suffers**

---

### Example - Bad Use Cases:

#### ❌ Multiple Statements:
```js
// ❌ Bad - trying to do too much
const result = age >= 18 ? 
  (console.log("Adult"), buyAlcohol(), goToParty(), "Allowed") : 
  (console.log("Minor"), stayHome(), "Not allowed");

// ✅ Better - use if-else
if (age >= 18) {
  console.log("Adult");
  buyAlcohol();
  goToParty();
  return "Allowed";
} else {
  console.log("Minor");
  stayHome();
  return "Not allowed";
}
```

---

#### ❌ Nested Ternaries (Hard to Read):
```js
// ❌ Bad - too confusing!
const grade = 
  score >= 90 ? "A" :
  score >= 80 ? "B" :
  score >= 70 ? "C" :
  score >= 60 ? "D" : "F";

// ✅ Better - use if-else or switch
let grade;
if (score >= 90) grade = "A";
else if (score >= 80) grade = "B";
else if (score >= 70) grade = "C";
else if (score >= 60) grade = "D";
else grade = "F";
```

**Exception:** Sometimes nested ternaries are OK if well-formatted:
```js
// ✅ Acceptable (each on new line, clear logic)
const message = 
  temperature > 30 ? "Too hot!" :
  temperature > 20 ? "Perfect!" :
  temperature > 10 ? "A bit cold" :
  "Freezing!";
```

---

#### ❌ Complex Conditions:
```js
// ❌ Bad - too complex
const access = 
  (user.isAdmin && user.isActive && !user.isBanned) || 
  (user.isPremium && user.hasValidSubscription) ? 
  "granted" : 
  "denied";

// ✅ Better - use if-else with named variables
const isAdminWithAccess = user.isAdmin && user.isActive && !user.isBanned;
const isPremiumActive = user.isPremium && user.hasValidSubscription;

const access = isAdminWithAccess || isPremiumActive ? "granted" : "denied";

// ✅ Even better - use if-else for clarity
let access;
if (user.isAdmin && user.isActive && !user.isBanned) {
  access = "granted";
} else if (user.isPremium && user.hasValidSubscription) {
  access = "granted";
} else {
  access = "denied";
}
```

---

## 🎯 Real-World Examples

### Example 1: User Status Badge
```js
const user = {
  name: "Sarah",
  isOnline: true
};

const statusBadge = user.isOnline ? "🟢 Online" : "⚫ Offline";

console.log(`${user.name}: ${statusBadge}`);
// Sarah: 🟢 Online
```

---

### Example 2: Price with Discount
```js
const price = 100;
const isMember = true;

const finalPrice = isMember ? price * 0.9 : price;

console.log(`Price: $${finalPrice}`);
// Price: $90
```

---

### Example 3: Form Validation Message
```js
const email = "user@example.com";
const isValid = email.includes("@");

console.log(`Email: ${isValid ? "✅ Valid" : "❌ Invalid"}`);
// Email: ✅ Valid
```

---

### Example 4: Dynamic CSS Class
```js
const score = 85;
const className = score >= 60 ? "pass" : "fail";

console.log(`<div class="${className}">Your score: ${score}</div>`);
// <div class="pass">Your score: 85</div>
```

---

### Example 5: API Response Handling
```js
const response = {
  status: 200,
  data: { name: "John" }
};

const result = response.status === 200 ? response.data : null;

console.log(result);
// { name: "John" }
```

---

### Example 6: Pluralization
```js
const itemCount = 5;

console.log(`You have ${itemCount} item${itemCount !== 1 ? "s" : ""}`);
// You have 5 items

// With 1 item:
const singleItem = 1;
console.log(`You have ${singleItem} item${singleItem !== 1 ? "s" : ""}`);
// You have 1 item
```

---

### Example 7: Time-based Greeting
```js
const getGreeting = (hour) => {
  return `Good ${hour < 12 ? "morning" : hour < 18 ? "afternoon" : "evening"}!`;
};

console.log(getGreeting(10)); // Good morning!
console.log(getGreeting(15)); // Good afternoon!
console.log(getGreeting(20)); // Good evening!
```

---

## 📝 Practice Exercises

### Exercise 1: Basic Ternary
```js
const temperature = 25;

// Use ternary to set message:
// temperature > 20 → "Warm"
// else → "Cold"
```

<details>
<summary>Click to see answer</summary>
```js
const temperature = 25;
const message = temperature > 20 ? "Warm" : "Cold";

console.log(message); // "Warm"
```

</details>

---

### Exercise 2: In Template Literal
```js
const age = 16;

// Complete this using ternary:
console.log(`You ${/* ternary here */} vote`);
// Should print: "You cannot vote" if age < 18
// Should print: "You can vote" if age >= 18
```

<details>
<summary>Click to see answer</summary>
```js
const age = 16;

console.log(`You ${age >= 18 ? "can" : "cannot"} vote`);
// You cannot vote
```

</details>

---

### Exercise 3: Convert if-else to Ternary
```js
let price = 50;
let discount;

if (price > 100) {
  discount = 20;
} else {
  discount = 10;
}

// Convert to ternary
```

<details>
<summary>Click to see answer</summary>
```js
const price = 50;
const discount = price > 100 ? 20 : 10;

console.log(discount); // 10
```

</details>

---

### Exercise 4: What's the Output?
```js
const x = 10;
const y = 20;

const result = x > y ? x : y;

console.log(result);
```

<details>
<summary>Click to see answer</summary>
```js
20
```

**Why?**
- `x > y` → `10 > 20` → `false`
- So return `y` → `20`

**This is a simple max() function!**

</details>

---

### Exercise 5: Fix the Mistake

What's wrong with this code?
```js
const age = 20;

const message = age >= 18 ? console.log("Adult");

console.log(message);
```

<details>
<summary>Click to see answer</summary>

**Problem:** Ternary needs both true AND false values (missing `:` false part)

**Fixed:**
```js
const age = 20;

const message = age >= 18 ? "Adult" : "Minor";

console.log(message); // "Adult"
```

Or if you want to use console.log:
```js
const age = 20;

age >= 18 ? console.log("Adult") : console.log("Minor");
// Adult
```

</details>

---

### Exercise 6: Advanced - Multiple Conditions
```js
const hour = 14;

// Create a greeting based on time:
// 0-11: "Good morning"
// 12-17: "Good afternoon"
// 18-23: "Good evening"

// Use ternary
```

<details>
<summary>Click to see answer</summary>
```js
const hour = 14;

const greeting = 
  hour < 12 ? "Good morning" :
  hour < 18 ? "Good afternoon" :
  "Good evening";

console.log(greeting); // "Good afternoon"
```

**Note:** This works but can be hard to read. For complex cases, if-else might be better!

</details>

---

## 🚨 Common Mistakes

### Mistake 1: Missing the False Part
```js
// ❌ Wrong - incomplete ternary
const result = age >= 18 ? "Adult";

// ✅ Correct - must have both parts
const result = age >= 18 ? "Adult" : "Minor";
```

---

### Mistake 2: Using Statements Instead of Expressions
```js
// ❌ Wrong - can't use statements
const result = age >= 18 ? let x = 5 : let x = 10;

// ✅ Correct - use expressions
const result = age >= 18 ? 5 : 10;
```

---

### Mistake 3: Too Complex Nesting
```js
// ❌ Hard to read
const x = a ? b ? c : d : e ? f : g;

// ✅ Better - use if-else
let x;
if (a) {
  x = b ? c : d;
} else {
  x = e ? f : g;
}
```

---

### Mistake 4: Forgetting Parentheses in Complex Conditions
```js
// ❌ Unclear
const result = age >= 18 && hasLicense ? "can drive" : "cannot drive";

// ✅ Clearer with parentheses
const result = (age >= 18 && hasLicense) ? "can drive" : "cannot drive";
```

---

### Mistake 5: Using for Side Effects Only
```js
// ❌ Bad practice - use if-else for side effects
age >= 18 ? console.log("Adult") : console.log("Minor");

// ✅ Better - use if-else
if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}

// ✅ Or save the value first
const status = age >= 18 ? "Adult" : "Minor";
console.log(status);
```

---

## 💎 Pro Tips

### Tip 1: Use Parentheses for Clarity
```js
// ❌ Harder to read
const result = condition1 && condition2 ? value1 : value2;

// ✅ Easier to read
const result = (condition1 && condition2) ? value1 : value2;
```

---

### Tip 2: Format Multi-line Ternaries
```js
// ❌ Hard to read
const message = longCondition ? "This is a very long true value" : "This is a very long false value";

// ✅ Better formatting
const message = longCondition
  ? "This is a very long true value"
  : "This is a very long false value";
```

---

### Tip 3: Name Complex Conditions
```js
// ❌ Hard to understand
const access = user.role === "admin" && user.active && !user.banned ? "full" : "limited";

// ✅ Easier to understand
const isActiveAdmin = user.role === "admin" && user.active && !user.banned;
const access = isActiveAdmin ? "full" : "limited";
```

---

### Tip 4: Use for Default Values
```js
// ✅ Great for defaults
const username = inputName ? inputName : "Guest";

// ✅ Even shorter with nullish coalescing
const username = inputName ?? "Guest";

// ✅ Or logical OR (but watch for falsy values!)
const username = inputName || "Guest";
```

---

### Tip 5: Combine with Logical Operators
```js
// Short-circuit evaluation + ternary
const message = isLoggedIn && user ? `Welcome ${user.name}` : "Please log in";

// Nullish coalescing + ternary
const price = discount ?? (isMember ? 90 : 100);
```

---

## 🎯 Real-World Example: Form Validation
```js
function validateForm(formData) {
  const emailValid = formData.email.includes("@");
  const passwordValid = formData.password.length >= 8;
  const nameValid = formData.name.trim().length > 0;

  // Using ternaries for validation messages
  const emailMessage = emailValid 
    ? "✅ Email is valid" 
    : "❌ Email must contain @";

  const passwordMessage = passwordValid
    ? "✅ Password is valid"
    : "❌ Password must be at least 8 characters";

  const nameMessage = nameValid
    ? "✅ Name is valid"
    : "❌ Name cannot be empty";

  // Overall validation
  const isFormValid = emailValid && passwordValid && nameValid;

  return {
    valid: isFormValid,
    messages: {
      email: emailMessage,
      password: passwordMessage,
      name: nameMessage
    },
    submitButton: isFormValid ? "enabled" : "disabled"
  };
}

// Usage
const form = {
  email: "user@example.com",
  password: "secret123",
  name: "John"
};

const validation = validateForm(form);
console.log(validation);
/*
{
  valid: true,
  messages: {
    email: "✅ Email is valid",
    password: "✅ Password is valid",
    name: "✅ Name is valid"
  },
  submitButton: "enabled"
}
*/
```

---

## 🎯 Real-World Example: React Component
```jsx
// Using ternary in React
function UserProfile({ user }) {
  return (
    <div className={user.isPremium ? "premium-user" : "regular-user"}>
      <h2>{user.name}</h2>
      
      {/* Conditional rendering */}
      {user.isOnline ? (
        <span className="status-online">🟢 Online</span>
      ) : (
        <span className="status-offline">⚫ Offline</span>
      )}
      
      {/* Inline conditional */}
      <p>
        Member since: {user.joinDate || "Unknown"}
        {user.isPremium ? " ⭐ Premium" : ""}
      </p>
      
      {/* Conditional button */}
      <button disabled={!user.canEdit}>
        {user.canEdit ? "Edit Profile" : "View Only"}
      </button>
    </div>
  );
}
```

---

## 🧠 Summary

### The Ternary Operator:
```js
condition ? expressionIfTrue : expressionIfFalse
```

---

### Key Points:

✅ **Shortcut** for simple if-else  
✅ Returns a **value** (expression, not statement)  
✅ Has **three parts** (ternary = three)  
✅ Perfect for **assignments** and **template literals**  
✅ Use for **simple** decisions  
✅ Avoid for **complex** logic  
✅ One line, but **don't sacrifice readability**  
✅ **Not a replacement** for if-else, just a tool

---

### When to Use:

| Scenario | Use Ternary? |
|----------|--------------|
| Simple assignment | ✅ Yes |
| Inside template literal | ✅ Yes |
| Function return | ✅ Yes |
| Multiple statements | ❌ No (use if-else) |
| Complex logic | ❌ No (use if-else) |
| Deeply nested | ❌ No (hard to read) |

---

## 📚 Resources

- [MDN: Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
- [JavaScript.info: Conditional operator](https://javascript.info/ifelse#conditional-operator)
- [W3Schools: JavaScript Ternary](https://www.w3schools.com/js/js_comparisons.asp)

---

## 🏷️ Tags

`#JavaScript` `#TernaryOperator` `#ConditionalOperator` `#Expressions` `#ControlFlow` `#Programming` `#Fundamentals`

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
- Nullish coalescing operator (`??`)
- Optional chaining (`?.`)
- Logical assignment operators

---

**⭐ If you found this helpful, please star this repo!**

**💬 Questions? Open an issue or discussion!**

**🔗 Share with others learning JavaScript!**

**🎯 Practice using ternary for cleaner code!**
