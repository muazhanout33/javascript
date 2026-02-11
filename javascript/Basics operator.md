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
