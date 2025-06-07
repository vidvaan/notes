# Day 24: JavaScript Events

Welcome to Day 24! Today you'll learn about **events** in JavaScript—how to make your web page respond to user actions like button clicks, input changes, mouse movement, and more.

---

## 1. What is an Event?

An **event** is something that happens in the browser:  
- The user clicks a button  
- The mouse moves over an element  
- The user types in a text box  
- The page finishes loading  
- ...and many more!

You can use JavaScript to **react** to these events.

---

## 2. Common Event Types

| Event Name   | When it Happens                          |
|--------------|------------------------------------------|
| `click`      | User clicks an element (button, link, etc.) |
| `input`      | User types or edits an `<input>` or `<textarea>` |
| `change`     | User changes the value of a form element and moves focus away |
| `mouseover`  | Mouse pointer moves over an element      |
| `mouseout`   | Mouse pointer leaves an element          |
| `keydown`    | User presses a keyboard key              |
| `submit`     | A form is submitted                      |

---

## 3. Adding Event Listeners

The **best practice** is to use `.addEventListener()` to attach a function (the "event handler") to an element.

```javascript
element.addEventListener("eventType", functionToCall);
```

### Example: Click Event

```html
<button id="myBtn">Click me!</button>
<script>
  document.getElementById("myBtn").addEventListener("click", function() {
    alert("Button clicked!");
  });
</script>
```

---

### Example: Input Event

```html
<input id="nameInput" type="text" placeholder="Type your name..." />
<p id="greeting"></p>
<script>
  document.getElementById("nameInput").addEventListener("input", function() {
    const name = this.value;
    document.getElementById("greeting").textContent = "Hello, " + name + "!";
  });
</script>
```

---

### Example: Mouseover Event

```html
<div id="hoverMe" style="width:120px; height:40px; background:#90caf9;">Hover here</div>
<script>
  document.getElementById("hoverMe").addEventListener("mouseover", function() {
    this.style.background = "#1976d2";
    this.style.color = "#fff";
    this.textContent = "Mouse is over!";
  });
  document.getElementById("hoverMe").addEventListener("mouseout", function() {
    this.style.background = "#90caf9";
    this.style.color = "#000";
    this.textContent = "Hover here";
  });
</script>
```

---

### Example: Change Event

```html
<select id="colorSelect">
  <option value="red">Red</option>
  <option value="blue">Blue</option>
</select>
<div id="colorBox" style="width:60px; height:30px;"></div>
<script>
  document.getElementById("colorSelect").addEventListener("change", function() {
    document.getElementById("colorBox").style.background = this.value;
  });
</script>
```

---

## 4. Full Example: Multiple Events

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Events Example</title>
    <style>
      #log { margin-top: 12px; color: #1976d2; }
    </style>
  </head>
  <body>
    <button id="btn">Click me</button>
    <input id="textInput" type="text" placeholder="Type something..." />
    <div id="hoverBox" style="width:100px; height:40px; background:#ffe082; margin-top:8px;">Hover me</div>
    <div id="log"></div>
    <script>
      document.getElementById("btn").addEventListener("click", function() {
        document.getElementById("log").textContent = "Button was clicked!";
      });

      document.getElementById("textInput").addEventListener("input", function() {
        document.getElementById("log").textContent = "You typed: " + this.value;
      });

      document.getElementById("hoverBox").addEventListener("mouseover", function() {
        document.getElementById("log").textContent = "Mouse is over the box!";
      });
      document.getElementById("hoverBox").addEventListener("mouseout", function() {
        document.getElementById("log").textContent = "";
      });
    </script>
  </body>
</html>
```

---

## 5. Best Practices

- Use `.addEventListener()` instead of HTML event attributes (`onclick=""`) for clean, maintainable code.
- Use **named functions** for complex actions, especially if you need to remove them later.
- Remember: not all elements support all event types (e.g., `input` works on `<input>`, not `<div>`).

---

## 🎯 Task Checklist

- [x] Add a click event to a button.
- [x] Add an input event to a text field.
- [x] Add a mouseover event to an element.
- [x] Add a change event to a select box.

---

**Great job! Next, you’ll learn how to make your pages even more interactive with real-world event-driven features.**