# 🔁 Looping Through Arrays in JavaScript

One of the most common and important uses of a `for` loop is **looping through arrays** — going through each element one by one.

## 📦 Example Array

```js
const jonas = ["Jonas", "Schmedtmann", 46, "teacher", ["Michael", "Peter"]];
We want to print each element separately.
🔥 Basic for Loop for Arrays
JavaScriptfor (let i = 0; i < jonas.length; i++) {
  console.log(jonas[i]);
}
🧠 Why Start from 0?
Because JavaScript arrays are zero-based (indexing starts at 0).





























IndexValue0"Jonas"1"Schmedtmann"2463"teacher"4["Michael", "Peter"]
→ First element = index 0
📏 Why i < jonas.length?
Never hardcode the length like i < 5 ❌
Always use:
JavaScripti < jonas.length
Benefits:

If the array grows → code still works
If items are removed → code remains safe

🧪 Example Output
textJonas
Schmedtmann
46
teacher
["Michael", "Peter"]
📊 Creating a New Array from Another Array
Example: Get the type of each element
JavaScriptconst types = [];

for (let i = 0; i < jonas.length; i++) {
  types.push(typeof jonas[i]);
}

console.log(types);
Important Idea:
We are reading from the jonas array and building a new types array.
🚀 Real-World Example (Calculating Ages)
JavaScriptconst years = [1991, 2007, 1969, 2020];
const ages = [];

for (let i = 0; i < years.length; i++) {
  ages.push(2037 - years[i]);
}

console.log(ages);
Result:
JavaScript[46, 30, 68, 17]
⏭️ continue vs break




















KeywordMeaningExample Use CasecontinueSkip the current iterationSkip non-string valuesbreakStop the entire loop completelyStop when a certain condition is met
1. continue Example (Skip non-strings)
JavaScriptfor (let i = 0; i < jonas.length; i++) {
  if (typeof jonas[i] !== "string") continue;
  console.log(jonas[i]);
}
→ Only prints string values
2. break Example (Stop early)
JavaScriptfor (let i = 0; i < jonas.length; i++) {
  if (typeof jonas[i] === "number") break;
  console.log(jonas[i]);
}
→ Stops the loop when it encounters the first number
