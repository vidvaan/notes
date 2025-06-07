# Day 15: Introduction to JavaScript

Welcome to Day 15! Today, you’ll take your first step into the world of programming for the web by learning JavaScript. JavaScript brings interactivity, logic, and dynamic content to your web pages.

---

## 1. What is JavaScript?

**JavaScript** is a powerful, high-level programming language that runs in the browser. It allows you to create interactive websites, control multimedia, animate images, validate forms, and much more. It is one of the three core technologies of the web:

- **HTML** – Structure
- **CSS** – Styling
- **JavaScript** – Interactivity & Logic

---

## 2. Where to Include JavaScript in HTML

### a. Inline in HTML Elements

You can add JavaScript directly to HTML elements using event attributes like `onclick`:

```html
<button onclick="alert('Hello!')">Click Me</button>
```

### b. Inside `<script>` Tags

You can place JavaScript code between `<script>` tags either in the `<head>`, `<body>`, or at the end of the HTML document:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JS Example</title>
    <!-- Optionally in the head (not recommended for scripts that access the DOM) -->
    <script>
      // JavaScript code here
    </script>
  </head>
  <body>
    <h1>Welcome!</h1>
    <script>
      // JavaScript here runs as the page loads
      alert("Page loaded!");
    </script>
  </body>
</html>
```

**Best Practice:**  
For most cases, place your `<script>` tags just before the closing `</body>` tag. This ensures that the HTML is loaded before your script runs.

```html
<body>
  <!-- Page content -->
  <script>
    // JavaScript code
  </script>
</body>
```

### c. External JavaScript Files

You can write JavaScript in a separate `.js` file and include it with the `src` attribute:

```html
<script src="script.js"></script>
```

**Benefits:**  
- Keeps code organized and reusable
- Improves page performance (browsers can cache .js files)

---

## 3. Output in JavaScript

JavaScript has several ways to show output to users or developers:

### a. `alert()`

Displays a pop-up box with a message.

```javascript
alert("Hello, world!");
```

**Use for:** Quick notifications or debugging (not for user-friendly UIs).

---

### b. `console.log()`

Writes messages to the browser’s JavaScript console (press F12 or right-click → Inspect → Console).

```javascript
console.log("This is a message in the console.");
```

**Use for:** Debugging and checking variable values.

---

### c. `document.write()`

Writes directly into the HTML document (not commonly used in modern web development).

```javascript
document.write("<h2>Welcome to my website!</h2>");
```

**Use for:** Simple demos, but avoid for production code as it can overwrite your document.

---

## 4. Example: All Three Output Methods

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Output Example</title>
  </head>
  <body>
    <h1>JavaScript Output</h1>
    <button onclick="alert('Button Clicked!')">Show Alert</button>
    <script>
      // Alert
      alert('This is an alert box!');

      // Console log
      console.log('This goes to the browser console.');

      // Document write
      document.write('<p>This text is written by JavaScript!</p>');
    </script>
  </body>
</html>
```

---

## 5. Best Practices

- Prefer `console.log` for debugging.
- Use `alert` sparingly; it interrupts the user.
- Avoid `document.write` in modern web apps.
- Put your `<script>` tags at the end of `<body>` or use `defer`/`async` attributes for better performance.
- Use external `.js` files for larger scripts.

---

## 🎯 Task Checklist

- [x] Add a `<script>` tag to your HTML and write a simple JavaScript message.
- [x] Display a message with `alert()`.
- [x] Log a message with `console.log()`.
- [x] Use `document.write()` to add some text to the page.
- [x] Try placing your script in different parts of the HTML and observe the effect.

---

**Great job! You’ve just written your first JavaScript. Tomorrow, you’ll learn about variables and data types.**