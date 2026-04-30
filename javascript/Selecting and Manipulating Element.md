# 🧠 What is the DOM?

**DOM** stands for **Document Object Model**.

### 🔷 Simple Explanation

The DOM is a representation of your HTML page as a **tree** inside the browser, which allows JavaScript to:

- Read elements
- Modify elements
- Add or remove elements

---

## 🔷 1. Selecting an Element

To select an element from the page, we use:

```javascript
document.querySelector(".message")
Meaning: Get the first element that has the class message.

🔷 2. Reading Element Content
To read the text inside an element:
JavaScriptconsole.log(document.querySelector(".message").textContent);
This will print the current text content of the element.

🔷 3. Updating Element Content
You can also change the text directly:
JavaScriptdocument.querySelector(".message").textContent = "The correct number 🎉";
Now the text visible on the webpage will be updated immediately.

📌 Important Concept
If you do this:
JavaScriptlet msg = document.querySelector(".message").textContent;
You are only saving a copy of the text at that moment.
If the content changes later on the page, you need to read it again to get the updated value.

🔷 4. Working with Multiple Elements
Example HTML:
HTML<div class="number">13</div>
<span class="score">20</span>
In JavaScript:
JavaScriptdocument.querySelector(".number").textContent = 13;
document.querySelector(".score").textContent = 10;
This updates both values on the page.

🔷 5. Working with Input Fields
Input elements are handled a bit differently:
HTML<input class="guess" />
Reading the value:
JavaScriptconsole.log(document.querySelector(".guess").value);
Setting a new value:
JavaScriptdocument.querySelector(".guess").value = 23;

📌 Key Difference

Normal elements → Use textContent
Input fields → Use .value


🔥 Important Summary

DOM = The way to control and manipulate an HTML page using JavaScript
querySelector = Used to select elements
textContent = Used to read or change text in normal elements
.value = Used to read or change values in <input> fields
Modifying the page is done using the assignment operator =


Key Takeaway:
The DOM is your bridge to dynamically read and change anything on a webpage using JavaScript.
text---

You can copy and save this directly as `dom-basics.md`.

Would you like me to make a shorter version or add headings for better orga
