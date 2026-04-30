 🧠 What is the DOM?

**DOM** stands for **Document Object Model**.

## 📌 Simple Definition

The DOM is the browser's representation of an HTML document as a structured **tree of objects** that JavaScript can access and manipulate.

## 🎯 How It Works

When you write HTML like this:

```html
<h1>Hello</h1>
<p class="text">Hi</p>
The browser converts it into a DOM Tree:
textdocument
 └── html
      ├── head
      └── body
           ├── h1
           └── p

🌳 Understanding the DOM Tree
The DOM organizes elements like a family tree with these relationships:

Parent: The container element
Child: Elements directly inside another element
Sibling: Elements that share the same parent

Example:
HTML<body>
  <h1>Title</h1>
  <p>Hello</p>
</body>
In this example:

body is the parent
h1 and p are children of body
h1 and p are siblings


🔗 Why is the DOM Important?
It serves as the bridge between HTML and JavaScript, allowing JavaScript to read and modify the content of a webpage.
🔥 What Can You Do with the DOM?

Change Text ContentJavaScriptdocument.querySelector('h1').textContent = 'Hello Moaaz';
Change StylingJavaScriptdocument.querySelector('h1').style.color = 'red';
Change AttributesJavaScriptdocument.querySelector('img').src = 'new.png';


🧠 What is document?
document is a built-in object provided by the browser. It represents the entire HTML page and is the starting point for working with the DOM.
Example:
JavaScriptdocument.querySelector('.message')
This means: "Go to the page and find the element with class message."

⚠️ Important Note
❌ DOM is NOT JavaScript

JavaScript (ECMAScript) = The programming language
DOM = A Web API provided by the browser

JavaScript uses the DOM to interact with web pages.
🌐 What are Web APIs?
Web APIs are ready-made tools given by the browser that JavaScript can use.
Examples:

DOM
setTimeout() / setInterval()
fetch() (for API requests)
localStorage, navigator, etc.


🎯 Final Summary

HTML → Defines the structure
DOM → Creates an object representation (tree) of the HTML
JavaScript → Manipulates and controls the DOM
Web APIs → Tools provided by the browser (including the DOM)

The Big Picture:
textHTML → Browser → Creates DOM → JavaScript controls it

🔥 Key Takeaway
Every element in HTML becomes an object in the DOM.

You can now copy and save this as dom-explained.md
textWould you like a shorter version or one optimized for Obsidian/Notion? Let
