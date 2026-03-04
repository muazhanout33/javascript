Functions Calling Other Functions in JavaScript
🎯 Concept

In JavaScript, a function can call another function inside it.

This is extremely common and helps:

Break problems into smaller steps

Reuse logic

Avoid repeating code (DRY principle)

🍎 Example Scenario: Fruit Processor

Imagine a juice machine that:

Receives fruits

Cuts them into pieces

Makes juice

So we create:

A cutting function

A juice function that uses it

1️⃣ Helper Function (Cutting Fruit)
function cutFruitPieces(fruit) {
  return fruit * 4;
}

Meaning:

Each fruit → 4 pieces

2 fruits → 8 pieces

2️⃣ Main Function Calls Helper Function
function fruitProcessor(apples, oranges) {
  const applePieces = cutFruitPieces(apples);
  const orangePieces = cutFruitPieces(oranges);

  const juice = `Juice with ${applePieces} apple pieces and ${orangePieces} orange pieces`;
  return juice;
}

Here:

fruitProcessor calls cutFruitPieces

Twice (for apples and oranges)

▶️ Using the Function
console.log(fruitProcessor(2, 3));

Output:

Juice with 8 apple pieces and 12 orange pieces

Because:

Apples: 2 × 4 = 8

Oranges: 3 × 4 = 12

🔄 Data Flow Between Functions

Execution flow:

fruitProcessor(2, 3)
      ↓
cutFruitPieces(2)
      ↓
2 * 4 = 8
      ↓
applePieces = 8

Same happens for oranges.

🤔 Why Use Another Function?

We could write:

const applePieces = apples * 4;
const orangePieces = oranges * 4;

But separating logic into a function is better.

🧠 DRY Principle

DRY = Don't Repeat Yourself

If the cutting rule changes (4 → 3):

Without function ❌
You must change many places.

With function ✅
Change once:

function cutFruitPieces(fruit) {
  return fruit * 3;
}

Everything updates automatically.

🏆 Key Takeaways

Functions can call other functions

This is very common in JavaScript

Helps organize code

Reduces duplication

Follows DRY principle
