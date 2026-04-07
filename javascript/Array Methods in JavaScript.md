# Array Methods in JavaScript

In JavaScript, arrays come with built-in functions that you can use directly. These are called **methods**.

**Example:**
```javascript
friends.push("Ali");
```

Here, `push` is a method – basically a function attached to the array itself.

> 🟢 **Key point:** Anything you call like `friends.methodName()` is a method.

---

## 1️⃣ `push()` — Add to the end

```javascript
friends.push("Jay");
```

✅ **Result:**
```javascript
["muaz", "mero", "youssef", "Jay"]
```

✅ **Returns:** The new length of the array:
```javascript
const newLength = friends.push("Jay");
console.log(newLength); // 4
```

---

## 2️⃣ `unshift()` — Add to the beginning

```javascript
friends.unshift("John");
```

✅ **Result:**
```javascript
["John", "muaz", "mero", "youssef"]
```

✅ **Returns:** The new length again.

---

## 3️⃣ `pop()` — Remove from the end

```javascript
friends.pop();
```

✅ **Result:**
```javascript
["muaz", "mero", "youssef"]
```

✅ **Returns:** The removed element:
```javascript
const removed = friends.pop();
console.log(removed); // last element
```

---

## 4️⃣ `shift()` — Remove from the beginning

```javascript
friends.shift();
```

✅ **Result:**
```javascript
["mero", "youssef"]
```

✅ **Returns:** The removed element from the start.

---

## 5️⃣ `indexOf()` — Find the position of an element

```javascript
friends.indexOf("youssef");
```

✅ **Returns:** The index of the element:
```
2
```

If the element is not found:
```
-1
```

---

## 6️⃣ `includes()` — Check if element exists

```javascript
friends.includes("youssef");
```

✅ **Returns:** `true` or `false`

> ⚠️ **Important note:**
> ```javascript
> friends.push(23);
> 
> friends.includes("23"); // ❌ false
> friends.includes(23);   // ✅ true
> ```
> **Why?** `includes` uses strict equality (`===`) – a string is NOT the same as a number.

💡 **Practical usage:**
```javascript
if (friends.includes("youssef")) {
  console.log("You have a friend called youssef");
}
```

---

## 🔥 Quick Summary

| Method | Does what? |
|---|---|
| `push()` | Add to the end |
| `unshift()` | Add to the beginning |
| `pop()` | Remove from the end |
| `shift()` | Remove from the beginning |
| `indexOf()` | Returns element index |
| `includes()` | Returns `true` or `false` |
