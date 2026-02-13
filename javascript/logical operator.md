# 🔗 Logical Operators in JavaScript

## 📚 Introduction

**Logical operators** allow you to combine multiple **boolean conditions** to make complex decisions.

In this lesson, we'll learn the three main logical operators:
- `&&` (AND)
- `||` (OR)
- `!` (NOT)

---

## 🎯 Boolean Variables

Let's start with three boolean variables:
```js
let hasDriverLicense = true;
let hasGoodVision = true;
let isTired = false;
```

Each variable can only be:
- `true` ✅
- `false` ❌

---

## 🔗 1. AND Operator `&&`

The AND operator returns `true` **only if BOTH conditions are true**.

### Syntax:
```js
condition1 && condition2
```

### Example:
```js
console.log(hasDriverLicense && hasGoodVision);
// true && true = true
```

---

### 📊 Truth Table for AND (`&&`)

| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| `true` | `true` | `true` ✅ |
| `true` | `false` | `false` ❌ |
| `false` | `true` | `false` ❌ |
| `false` | `false` | `false` ❌ |

### 💡 Remember:
> **ALL conditions must be true for AND to return true**

---

### More Examples:
```js
console.log(true && true);    // true
console.log(true && false);   // false
console.log(false && true);   // false
console.log(false && false);  // false
```

---

### Real Example:
```js
let age = 25;
let hasLicense = true;

console.log(age >= 18 && hasLicense);
// true && true = true
```

---

## 🔀 2. OR Operator `||`

The OR operator returns `true` **if at least ONE condition is true**.

### Syntax:
```js
condition1 || condition2
```

### Example:
```js
console.log(hasDriverLicense || hasGoodVision);
// true || true = true
```

---

### 📊 Truth Table for OR (`||`)

| Condition 1 | Condition 2 | Result |
|-------------|-------------|--------|
| `true` | `true` | `true` ✅ |
| `true` | `false` | `true` ✅ |
| `false` | `true` | `true` ✅ |
| `false` | `false` | `false` ❌ |

### 💡 Remember:
> **At least ONE condition must be true for OR to return true**

---

### More Examples:
```js
console.log(true || true);    // true
console.log(true || false);   // true
console.log(false || true);   // true
console.log(false || false);  // false
```

---

### Real Example:
```js
let isMember = false;
let hasDiscount = true;

console.log(isMember || hasDiscount);
// false || true = true (discount applies!)
```

---

## 🔁 3. NOT Operator `!`

The NOT operator **reverses** a boolean value.

### Syntax:
```js
!condition
```

### Example:
```js
console.log(!hasDriverLicense);
// !true = false
```

---

### 📊 Truth Table for NOT (`!`)

| Original | Result |
|----------|--------|
| `true` | `false` |
| `false` | `true` |

---

### More Examples:
```js
console.log(!true);    // false
console.log(!false);   // true

let isRaining = false;
console.log(!isRaining); // true (it's NOT raining)
```

---

### Double NOT (`!!`):
```js
console.log(!!true);   // true
console.log(!!false);  // false

// Often used to convert values to boolean
console.log(!!"hello"); // true (non-empty string is truthy)
console.log(!!0);       // false (0 is falsy)
```

---

## 🚗 Decision Example: Should Sara Drive?

Let's use logical operators to make a real decision!

### Rule:
> Sara should drive if she has a **driver's license** AND **good vision**

---

### Method 1: Store in Variable
```js
let hasDriverLicense = true;
let hasGoodVision = true;

let shouldDrive = hasDriverLicense && hasGoodVision;

if (shouldDrive) {
  console.log("Sara can drive 🚗");
} else {
  console.log("Someone else should drive");
}
```

---

### Method 2: Direct in if Statement
```js
if (hasDriverLicense && hasGoodVision) {
  console.log("Sara can drive 🚗");
} else {
  console.log("Someone else should drive");
}
```

Both are correct! Choose based on readability.

---

## ➕ Adding a Third Condition

### New Rule:
> Sara should drive if she has:
> - Driver's license ✅
> - Good vision ✅
> - NOT tired ✅
```js
let hasDriverLicense = true;
let hasGoodVision = true;
let isTired = false;

if (hasDriverLicense && hasGoodVision && !isTired) {
  console.log("Sara can drive 🚗");
} else {
  console.log("Someone else should drive 🚫");
}
```

---

## 🔍 Step-by-Step Evaluation

### Scenario 1: Sara is Tired
```js
hasDriverLicense = true;
hasGoodVision = true;
isTired = true;
```

**Condition:**
```js
hasDriverLicense && hasGoodVision && !isTired
```

**Step 1:** Evaluate `!isTired`
```js
!true = false
```

**Step 2:** Evaluate AND
```js
true && true && false = false
```

**Result:**
```
Someone else should drive 🚫
```

---

### Scenario 2: Sara is NOT Tired
```js
hasDriverLicense = true;
hasGoodVision = true;
isTired = false;
```

**Condition:**
```js
hasDriverLicense && hasGoodVision && !isTired
```

**Step 1:** Evaluate `!isTired`
```js
!false = true
```

**Step 2:** Evaluate AND
```js
true && true && true = true
```

**Result:**
```
Sara can drive 🚗
```

---

## 🎨 Visual Representation

### AND (`&&`) - All Must Be True:
```
Condition 1  Condition 2  Condition 3    Result
    ✅    &&     ✅     &&     ✅      =    ✅
    ✅    &&     ✅     &&     ❌      =    ❌
    ✅    &&     ❌     &&     ✅      =    ❌
    ❌    &&     ✅     &&     ✅      =    ❌
```

---

### OR (`||`) - At Least One Must Be True:
```
Condition 1  Condition 2  Condition 3    Result
    ✅    ||     ✅     ||     ✅      =    ✅
    ✅    ||     ✅     ||     ❌      =    ✅
    ✅    ||     ❌     ||     ❌      =    ✅
    ❌    ||     ❌     ||     ❌      =    ❌
```

---

## 🔥 Real Programming Examples

### Example 1: User Access Control
```js
let userLoggedIn = true;
let hasSubscription = true;
let isBanned = false;

if (userLoggedIn && hasSubscription && !isBanned) {
  console.log("✅ Access granted");
} else {
  console.log("❌ Access denied");
}
```

---

### Example 2: Form Validation
```js
let hasEmail = true;
let hasPassword = true;
let agreedToTerms = true;

if (hasEmail && hasPassword && agreedToTerms) {
  console.log("✅ Form is valid");
} else {
  console.log("❌ Please fill all required fields");
}
```

---

### Example 3: Discount Eligibility
```js
let isStudent = false;
let isSenior = false;
let hasCoupon = true;

if (isStudent || isSenior || hasCoupon) {
  console.log("🎉 You get a discount!");
} else {
  console.log("Regular price applies");
}
```

---

### Example 4: Weather Check
```js
let isSunny = true;
let isWeekend = true;
let hasFreetime = true;

if (isSunny && isWeekend && hasFreetime) {
  console.log("🏖️ Perfect day for the beach!");
} else {
  console.log("Maybe another day");
}
```

---

## 🎯 Combining AND and OR

You can combine `&&` and `||` in the same expression!

### Example:
```js
let age = 25;
let hasParentPermission = false;

// Can enter if: (age >= 18) OR (age >= 13 AND has parent permission)
if (age >= 18 || (age >= 13 && hasParentPermission)) {
  console.log("✅ Can enter");
} else {
  console.log("❌ Cannot enter");
}
```

---

### ⚠️ Important: Use Parentheses for Clarity
```js
// ❌ Unclear (what's evaluated first?)
if (a && b || c && d) { }

// ✅ Clear (parentheses show intention)
if ((a && b) || (c && d)) { }
```

---

## 📊 Operator Precedence

When mixing logical operators, JavaScript follows this order:

1. **`!`** (NOT) - Highest priority
2. **`&&`** (AND) - Medium priority
3. **`||`** (OR) - Lowest priority

### Example:
```js
let result = !false && true || false;
```

**Evaluation order:**
```js
// Step 1: ! (NOT)
!false = true

// Step 2: && (AND)
true && true = true

// Step 3: || (OR)
true || false = true
```

**Result:** `true`

---

### Best Practice: Use Parentheses
```js
// Works but unclear
let result = !a && b || c;

// Better - shows intention
let result = ((!a) && b) || c;
```

---

## 📝 Practice Exercises

### Exercise 1: Basic AND
```js
let isAdult = true;
let hasTicket = true;

// What will this print?
console.log(isAdult && hasTicket);
```

<details>
<summary>Click to see answer</summary>
```js
true
```

**Why?** Both conditions are `true`, so AND returns `true`.

</details>

---

### Exercise 2: Basic OR
```js
let knowsJavaScript = false;
let knowsPython = true;

// What will this print?
console.log(knowsJavaScript || knowsPython);
```

<details>
<summary>Click to see answer</summary>
```js
true
```

**Why?** At least one condition is `true`, so OR returns `true`.

</details>

---

### Exercise 3: NOT Operator
```js
let isRaining = true;

// What will this print?
console.log(!isRaining);
```

<details>
<summary>Click to see answer</summary>
```js
false
```

**Why?** NOT reverses the value: `!true = false`.

</details>

---

### Exercise 4: Complex Condition
```js
let age = 16;
let hasLicense = false;
let hasParent = true;

// Can drive if: (age >= 18 AND hasLicense) OR (age >= 16 AND hasParent)
if ((age >= 18 && hasLicense) || (age >= 16 && hasParent)) {
  console.log("Can drive");
} else {
  console.log("Cannot drive");
}
```

**What will this print?**

<details>
<summary>Click to see answer</summary>
```js
Can drive
```

**Why?**
- First part: `(16 >= 18 && false)` = `false && false` = `false`
- Second part: `(16 >= 16 && true)` = `true && true` = `true`
- Final: `false || true` = `true`

</details>

---

### Exercise 5: Tricky NOT
```js
let a = true;
let b = false;

console.log(!a && !b);
console.log(!(a && b));
```

**What's the difference?**

<details>
<summary>Click to see answer</summary>
```js
!a && !b
= !true && !false
= false && true
= false

!(a && b)
= !(true && false)
= !false
= true
```

**Lesson:** Parentheses matter! NOT applies to different parts.

</details>

---

## 🚨 Common Mistakes

### Mistake 1: Confusing `&&` and `||`
```js
// ❌ Wrong logic
if (age > 18 || hasLicense) {
  // This allows people over 18 WITHOUT a license!
}

// ✅ Correct
if (age >= 18 && hasLicense) {
  console.log("Can drive");
}
```

---

### Mistake 2: Forgetting NOT operator
```js
let isClosed = true;

// ❌ Wrong
if (isClosed) {
  console.log("Store is open");
}

// ✅ Correct
if (!isClosed) {
  console.log("Store is open");
}
```

---

### Mistake 3: Not Using Parentheses
```js
// ❌ Unclear
if (a && b || c && d) { }

// ✅ Clear
if ((a && b) || (c && d)) { }
```

---

### Mistake 4: Assignment Instead of Comparison
```js
let isLoggedIn = true;

// ❌ Wrong (assignment!)
if (isLoggedIn = false) {
  console.log("Logged out");
}

// ✅ Correct (comparison)
if (isLoggedIn === false) {
  console.log("Logged out");
}

// ✅ Even better (using NOT)
if (!isLoggedIn) {
  console.log("Logged out");
}
```

---

## 💎 Pro Tips

### Tip 1: Name Boolean Variables Clearly
```js
// ❌ Bad names
let a = true;
let status = false;

// ✅ Good names (ask yes/no questions)
let isActive = true;
let hasPermission = false;
let canEdit = true;
let shouldNotify = false;
```

---

### Tip 2: Short-Circuit Evaluation

JavaScript evaluates AND and OR from left to right and **stops as soon as the result is known**.

#### AND Short-Circuit:
```js
// If first is false, second is never checked
false && expensiveFunction() // expensiveFunction() NOT called!
```

#### OR Short-Circuit:
```js
// If first is true, second is never checked
true || expensiveFunction() // expensiveFunction() NOT called!
```

---

### Tip 3: Use Meaningful Variable Names
```js
// ❌ Hard to read
if (a && b && !c) { }

// ✅ Easy to read
let hasPermission = true;
let isVerified = true;
let isBanned = false;

if (hasPermission && isVerified && !isBanned) {
  console.log("Access granted");
}
```

---

### Tip 4: Extract Complex Conditions
```js
// ❌ Hard to read
if (age >= 18 && hasLicense && !isSuspended && hasInsurance && carWorks) {
  console.log("Can drive");
}

// ✅ Easier to read
let meetsAgeRequirement = age >= 18;
let hasValidLicense = hasLicense && !isSuspended;
let carIsReady = hasInsurance && carWorks;

if (meetsAgeRequirement && hasValidLicense && carIsReady) {
  console.log("Can drive");
}
```

---

## 🎯 Real-World Example: Login System
```js
// User login validation
let username = "john_doe";
let password = "secret123";
let isEmailVerified = true;
let accountLocked = false;
let tooManyAttempts = false;

// Check all conditions
let hasCredentials = username && password;
let accountIsValid = isEmailVerified && !accountLocked;
let canAttemptLogin = !tooManyAttempts;

if (hasCredentials && accountIsValid && canAttemptLogin) {
  console.log("✅ Login successful!");
  console.log(`Welcome back, ${username}!`);
} else {
  // Provide specific error messages
  if (!hasCredentials) {
    console.log("❌ Please enter username and password");
  } else if (!isEmailVerified) {
    console.log("❌ Please verify your email first");
  } else if (accountLocked) {
    console.log("❌ Account is locked. Contact support");
  } else if (tooManyAttempts) {
    console.log("❌ Too many login attempts. Try again later");
  }
}
```

---

## 🎯 Real-World Example: E-commerce Discount
```js
// Discount eligibility
let isFirstPurchase = true;
let cartTotal = 150;
let hasCoupon = false;
let isVIP = false;
let isBirthday = false;

// Different discount scenarios
let qualifiesForNewCustomer = isFirstPurchase && cartTotal >= 100;
let qualifiesForVIP = isVIP;
let qualifiesForBirthday = isBirthday;
let qualifiesForCoupon = hasCoupon;

let getsDiscount = qualifiesForNewCustomer || 
                   qualifiesForVIP || 
                   qualifiesForBirthday || 
                   qualifiesForCoupon;

if (getsDiscount) {
  console.log("🎉 Congratulations! You get a discount!");
  
  if (qualifiesForNewCustomer) {
    console.log("15% off for first purchase over $100");
  }
  if (qualifiesForVIP) {
    console.log("20% VIP discount");
  }
  if (qualifiesForBirthday) {
    console.log("Happy birthday! 10% off");
  }
  if (qualifiesForCoupon) {
    console.log("Coupon discount applied");
  }
} else {
  console.log("Regular price applies");
}
```

---

## 📊 Quick Reference Table

### Logical Operators:

| Operator | Name | Returns true when | Example |
|----------|------|-------------------|---------|
| `&&` | AND | **All** conditions are true | `true && true` → `true` |
| `\|\|` | OR | **At least one** condition is true | `true \|\| false` → `true` |
| `!` | NOT | Reverses the value | `!true` → `false` |

---

### Truth Tables Summary:
```js
// AND (&&)
true  && true  = true
true  && false = false
false && true  = false
false && false = false

// OR (||)
true  || true  = true
true  || false = true
false || true  = true
false || false = false

// NOT (!)
!true  = false
!false = true
```

---

## ✅ Summary

### Key Takeaways:

✅ **`&&` (AND)** = ALL conditions must be true  
✅ **`||` (OR)** = At least ONE condition must be true  
✅ **`!` (NOT)** = Reverses boolean value  
✅ Use parentheses for clarity when combining operators  
✅ Operator precedence: `!` > `&&` > `||`  
✅ Short-circuit evaluation stops when result is known  
✅ Name boolean variables with `is`, `has`, `can`, `should`  
✅ Extract complex conditions into named variables  
✅ Logical operators = core of decision-making in programming

---

## 🧠 How This Works in Real Systems
```js
// Authentication & Authorization
if (userLoggedIn && hasSubscription && !isBanned) {
  access = true;
}

// Form Validation
if (hasName && hasEmail && hasPassword && agreedToTerms) {
  submitForm();
}

// Feature Flags
if (isProduction && featureEnabled && !underMaintenance) {
  showNewFeature();
}

// Safety Checks
if (hasPermission && isVerified && !isExpired && hasAccess) {
  allowOperation();
}
```

**This is how real applications make decisions!** 🔥

---

## 📚 Resources

- [MDN: Logical Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)
- [JavaScript.info: Logical Operators](https://javascript.info/logical-operators)
- [MDN: Operator Precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
- [W3Schools: JavaScript Booleans](https://www.w3schools.com/js/js_booleans.asp)

---

## 🏷️ Tags

`#JavaScript` `#LogicalOperators` `#Boolean` `#AND` `#OR` `#NOT` `#Conditionals` `#Programming` `#Fundamentals`

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
- Switch statements
- Ternary operator (`? :`)
- Nullish coalescing (`??`)

---

**⭐ If you found this helpful, please star this repo!**

**💬 Questions? Open an issue or discussion!**

**🔗 Share with others learning JavaScript!**

**🎯 Practice these operators - they're fundamental to programming!**
