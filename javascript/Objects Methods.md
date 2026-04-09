# 🔥 Objects with Methods in JavaScript

Before this lesson, you knew that objects can store **data**:

```js
const jonas = {
  firstName: "Jonas",
  birthYear: 1991
};
💡 New Idea: Objects Can Also Store Functions!
JavaScriptconst jonas = {
  firstName: "Jonas",
  birthYear: 1991,

  calcAge: function(birthYear) {
    return 2037 - birthYear;
  }
};
📌 Here:

calcAge is a property name
Its value is a function

✅ A function stored inside an object is called a method.

🧠 How to Call a Method?
You call it just like accessing a regular property:
JavaScriptjonas.calcAge(1991);
You can also use bracket notation:
JavaScriptjonas["calcAge"](1991);

❌ Problem: Repetition (Violates DRY)
We had to write the birth year twice:
JavaScriptbirthYear: 1991
and
JavaScriptjonas.calcAge(1991)
This is bad practice — not maintainable and violates DRY (Don’t Repeat Yourself).

💡 Solution: The this Keyword
JavaScript gives us a special keyword: this
this means: "The object that is calling this method"
✨ Using this in a Method:
JavaScriptconst jonas = {
  firstName: "Jonas",
  birthYear: 1991,

  calcAge: function() {
    return 2037 - this.birthYear;
  }
};

this.birthYear refers to 1991
Because when the method runs, this === jonas

Example:
JavaScriptjonas.calcAge();   // 46
Who called the method? → jonas
So this points to the jonas object.

⚠️ Why Not Just Write jonas.birthYear?
JavaScriptreturn 2037 - jonas.birthYear;
❌ This is bad practice.
If you later rename the object or assign it to another variable:
JavaScriptconst jonas2 = jonas;
The code will break.
✅ this is smart — it automatically refers to the current object that called the method.

🚀 Performance Improvement: Store the Result
Instead of calculating the age every time:
JavaScriptjonas.calcAge();
jonas.calcAge();
jonas.calcAge();
We can calculate it once and store it inside the object:
JavaScriptconst jonas = {
  firstName: "Jonas",
  birthYear: 1991,

  calcAge: function() {
    this.age = 2037 - this.birthYear;   // store the result
    return this.age;
  }
};
Now you can do:
JavaScriptjonas.calcAge();        // calculates once
console.log(jonas.age); // uses the stored value (no recalculation)

🎯 Challenge: Create a getSummary Method
We want a method that returns:
"Jonas is a 46-year-old teacher, and he has a driver's license"
Solution:
JavaScriptconst jonas = {
  firstName: "Jonas",
  job: "teacher",
  birthYear: 1991,
  hasDriversLicense: true,

  calcAge: function() {
    this.age = 2037 - this.birthYear;
    return this.age;
  },

  getSummary: function() {
    return `${this.firstName} is a ${this.calcAge()}-year-old ${this.job}, and he ${
      this.hasDriversLicense ? "has" : "does not have"
    } a driver's license.`;
  }
};
JavaScriptconsole.log(jonas.getSummary());
Output:
textJonas is a 46-year-old teacher, and he has a driver's license.
🧠 Explanation

this.calcAge() → Calls another method inside the same object
this.hasDriversLicense ? "has" : "does not have" → Ternary operator for clean conditional text


🔥 Bonus: Arrays Are Also Objects 😳
When you write:
JavaScriptfriends.push("Ali");

friends is an object
push is a method

Arrays are just special objects with built-in methods.

🧾 Key Takeaways

Any function inside an object is called a method
this refers to the object that is calling the method
Always use this instead of hardcoding the object name
You can store computed values as new properties on the object
Methods can call other methods within the same object using this


Let me know if you want exercises or the next lesson (e.g., Object Methods + Loops, or Constructors)! 🚀
