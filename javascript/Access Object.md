# Accessing and Modifying Object Properties in JavaScript

In this lesson, you’ll learn how to:

- Retrieve data from objects
- Change (and add) data in objects

Using both **dot notation (`.`)** and **bracket notation (`[]`)**.

---

### 🔹 Reviewing the Jonas Object

From the previous lesson:

```js
const jonas = {
  firstName: "Jonas",
  lastName: "Schmedtmann",
  age: 2037 - 1991,
  job: "teacher",
  friends: ["Michael", "Peter", "Steven"]
};
Note: The order of properties doesn't matter in objects. We access values by property name, not by position.

🔹 Retrieving Data from Objects
1️⃣ Dot Notation (.)
JavaScriptconsole.log(jonas.lastName);     // Schmedtmann

Simple and readable.
Use it when you know the property name in advance (static).

2️⃣ Bracket Notation ([])
JavaScriptconsole.log(jonas["lastName"]);  // Schmedtmann

More flexible.
Allows you to use any expression that evaluates to a string.
Perfect for dynamic property names.

Example with a dynamic key:
JavaScriptconst key = "firstName";
console.log(jonas[key]);         // Jonas
Important: Dot notation cannot be used with dynamic expressions. Only bracket notation supports computed property access.

🔹 Dynamic User Input Example
JavaScriptconst interestedIn = prompt(
  "What do you want to know about Jonas? Choose between firstName, lastName, age, job, friends"
);

console.log(jonas[interestedIn]);

The user can type any property name.
Bracket notation makes this possible.
Dot notation would not work here.


🔹 Adding New Properties
You can add properties to an object even after it's created.
Using Dot Notation:
JavaScriptjonas.location = "Portugal";
Using Bracket Notation:
JavaScriptjonas["twitter"] = "@Jonasschmedtman";
Both methods work equally well.
Bracket notation is preferred when the property name is dynamic or contains special characters.

🔹 Challenge Example
Goal: Create this dynamic sentence using object data:
"Jonas has 3 friends, and his best friend is called Michael."
Solution:
JavaScriptconsole.log(
  `Jonas has ${jonas.friends.length} friends, ` +
  `and his best friend is called ${jonas.friends[0]}.`
);
Output:
textJonas has 3 friends, and his best friend is called Michael.
✅ No hard-coded values — everything is dynamically retrieved from the object.

🔹 Key Takeaways

Dot notation (.): Best for static property names that you know beforehand.
Bracket notation ([]): Best for dynamic or computed property names.

You can also combine both notations when working with nested data:
JavaScriptjonas.friends[0]        // → "Michael" (dot + bracket for array)
jonas["friends"][0]     // → same result
Tip: When accessing elements inside an array that is stored in an object, use bracket notation for the array index.

Happy coding! 🎉
