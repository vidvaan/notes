# Day 26: CSS with JavaScript

Welcome to Day 26! Today you'll learn how to dynamically change the appearance of your web page using JavaScript. This includes modifying **inline styles** and **CSS classes** on elements.

---

## 1. Modifying Inline Styles

You can directly change the style of an element using its `.style` property in JavaScript:

```javascript
let box = document.getElementById("myBox");
box.style.backgroundColor = "lightgreen";
box.style.borderRadius = "10px";
box.style.fontWeight = "bold";
```

- Style property names use **camelCase** (e.g., `backgroundColor`, not `background-color`).

---

## 2. Adding, Removing, and Toggling Classes

It's best practice to use CSS classes for most styling, then **add or remove classes** with JavaScript as needed.

### a. `classList.add()` and `classList.remove()`

```javascript
let el = document.getElementById("myBox");
el.classList.add("highlight");     // Adds the class
el.classList.remove("highlight");  // Removes the class
```

### b. `classList.toggle()`

Adds the class if it's not present, removes it if it is.

```javascript
el.classList.toggle("active");
```

---

## 3. Example: Dynamic CSS with JavaScript

```html
<!DOCTYPE html>
<html>
  <head>
    <title>CSS with JavaScript Example</title>
    <style>
      #myBox {
        width: 120px;
        height: 60px;
        background: #b3e5fc;
        line-height: 60px;
        text-align: center;
        font-size: 1.2em;
        margin: 20px auto;
        border-radius: 6px;
        transition: all 0.3s;
      }
      .highlight {
        background: #ffc107;
        color: #fff;
        font-weight: bold;
        box-shadow: 0 0 16px #ffd54f;
      }
      .rounded {
        border-radius: 30px;
      }
    </style>
  </head>
  <body>
    <div id="myBox">Hello!</div>
    <button onclick="toggleHighlight()">Toggle Highlight</button>
    <button onclick="makeRounded()">Make Rounded</button>
    <button onclick="changeInline()">Change Inline Style</button>
    <script>
      function toggleHighlight() {
        document.getElementById("myBox").classList.toggle("highlight");
      }
      function makeRounded() {
        document.getElementById("myBox").classList.add("rounded");
      }
      function changeInline() {
        let box = document.getElementById("myBox");
        box.style.backgroundColor = "#81c784";
        box.style.color = "#263238";
        box.style.fontSize = "1.5em";
      }
    </script>
  </body>
</html>
```

---

## 4. Removing All Classes

You can clear all classes from an element:

```javascript
el.className = "";
```

Or set multiple classes at once:

```javascript
el.className = "highlight rounded";
```

---

## 5. Best Practices

- Prefer using CSS classes for most visual changes, and toggle them with JS.
- Use `.style` for one-off changes or dynamic values.
- Use transitions in CSS for smooth effects.
- Keep your style logic in CSS, and your behavior logic in JS.

---

## 🎯 Task Checklist

- [x] Change element styles using `.style`
- [x] Add/remove/toggle CSS classes dynamically
- [x] Try combining both approaches for rich interactivity

---

**Awesome! Now you can create visually dynamic web pages with just a little JavaScript.**