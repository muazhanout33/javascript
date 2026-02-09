Writing in HTML & JavaScript

HTML is the main page, JavaScript must be linked to it.

Initially, you can write JS inside <script> tags in HTML (inline).

Example code from the lesson:
 ```js
<script>
  alert("JavaScript is fun");
</script>
```


This is quick for testing, but not practical for real development.

5️⃣ Viewing Results in the Browser

To see results of calculations or JS code, there are 2 ways:

Alert box: alert("...")

Console: console.log(...)

Example:
```js
console.log(40 + 8 + 23 - 10);
```

To open the browser console: F12 or right-click → Inspect → Console.

6️⃣ Using an External JS File

Benefits: separates HTML from JS logic, easier to maintain.

Steps:

Create a new JS file, e.g., script.js.

Move all JS code from the <script> tag into script.js.

Link it in HTML:

<script src="script.js"></script>


Place it at the end of the <body> tag.

File name is correct.

File is in the same folder.

No code errors.
