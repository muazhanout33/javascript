# 🔁 What is a While Loop in JavaScript?

A **while loop** is a loop that keeps running **as long as a condition is true**.

### Basic Syntax:

```javascript
while (condition) {
  // code to run
}

🆚 for vs while
✔️ for Loop
Use it when you know exactly how many times you want to repeat something.
JavaScriptfor (let i = 1; i <= 10; i++) {
  console.log(i);
}
✔️ while Loop
Use it when you don’t know how many times the loop will run.
JavaScriptlet i = 1;

while (i <= 10) {
  console.log(i);
  i++;
}

🧠 Key Idea
In a while loop, you must manually handle three things:

Initialization (setting the counter)
Condition (when to keep looping)
Increment / Update (changing the counter)

⚠️ Warning: If you forget the increment, you will create an infinite loop!

🎲 Real Example: Rolling a Dice
Goal: Keep rolling a dice until we get a 6.
JavaScriptlet dice = Math.trunc(Math.random() * 6) + 1;

while (dice !== 6) {
  console.log(`You rolled ${dice}`);

  dice = Math.trunc(Math.random() * 6) + 1;

  if (dice === 6) {
    console.log("Loop is about to end...");
  }
}
🧠 What’s happening?

We generate a random number between 1 and 6
We check: Is it NOT 6?
If yes → continue looping
If no → stop the loop

Each iteration, we roll the dice again

⚠️ Important Behavior:

If the first roll is 6, the loop won’t run at all (condition is false from the start).
If you never update the variable inside the loop → infinite loop.


📌 Main Takeaway

👉 Use while when you don’t know how many iterations you need.
👉 Use for when you do know the number of iterations.


Would you like me to add any of the following?

Simple practice exercises
Visual diagram explanation
More real-world examples (login attempts, games, etc.)

Just tell me! 👍
textCopy and paste this directly into a `.md` file. It’s clean, well-structured, and easy to read.

Want me to combine this with the previous loops content into one big Markdow
