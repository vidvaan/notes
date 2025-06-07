# Day 23: Manipulating the DOM

Welcome to Day 23! Now that you know how to select elements in the DOM, let’s learn how to **change their content, styles, and structure** using JavaScript.

---

## 1. Changing Text and HTML Content

### a. `.textContent`

Changes the *text* inside an element.

```javascript
document.getElementById("myPara").textContent = "New text here!";
```

### b. `.innerHTML`

Changes the *HTML* (including tags) inside an element.

```javascript
document.getElementById("myPara").innerHTML = "<b>Bold text!</b>";
```

---

## 2. Changing Styles

You can change an element’s CSS using the `.style` property:

```javascript
let box = document.getElementById("myBox");
box.style.backgroundColor = "yellow";
box.style.fontSize = "24px";
box.style.border = "2px solid blue";
```

---

## 3. Creating and Adding Elements

You can create new elements and add them to the page.

```javascript
// Create a new <li> element
let newItem = document.createElement("li");
newItem.textContent = "New List Item";

// Add it to an existing <ul>
document.getElementById("myList").appendChild(newItem);
```

---

## 4. Removing Elements

You can remove elements from the DOM.

```javascript
let item = document.getElementById("removeMe");
item.remove(); // Removes the element
```

Or, using the parent node:

```javascript
let parent = document.getElementById("myList");
let item = document.getElementById("item2");
parent.removeChild(item);
```

---

## 5. Example: Manipulating the DOM

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Manipulation Example</title>
    <style>
      .highlight { background: yellow; }
    </style>
  </head>
  <body>
    <h2 id="mainTitle">Hello, World!</h2>
    <p id="info">This is a paragraph.</p>
    <button onclick="changeText()">Change Text</button>
    <button onclick="addItem()">Add List Item</button>
    <button onclick="removeItem()">Remove List Item</button>
    <ul id="myList">
      <li id="item1">Item 1</li>
      <li id="item2">Item 2</li>
    </ul>
    <button onclick="highlightTitle()">Highlight Title</button>
    <script>
      // Change textContent and innerHTML
      function changeText() {
        document.getElementById("info").textContent = "The paragraph text is now different!";
        document.getElementById("mainTitle").innerHTML = "<i>Welcome!</i>";
      }

      // Create and append a new list item
      function addItem() {
        const li = document.createElement("li");
        li.textContent = "A new item!";
        document.getElementById("myList").appendChild(li);
      }

      // Remove the last list item
      function removeItem() {
        const list = document.getElementById("myList");
        if (list.lastElementChild) {
          list.removeChild(list.lastElementChild);
        }
      }

      // Change styles dynamically
      function highlightTitle() {
        const title = document.getElementById("mainTitle");
        title.classList.toggle("highlight");
        title.style.color = title.style.color === "red" ? "" : "red";
      }
    </script>
  </body>
</html>
```

---

## 6. Best Practices

- Use `.textContent` to avoid accidentally inserting unwanted HTML.
- Use `.innerHTML` if you want to insert HTML tags.
- Use `.style` for quick inline style changes; for more complex styling, consider toggling CSS classes with `element.classList.add/remove/toggle`.
- Always check if elements exist before manipulating them.

---

## 🎯 Task Checklist

- [x] Change the text or HTML of an element using JS.
- [x] Change an element’s style using JS.
- [x] Create a new element and add it to the page.
- [x] Remove an element from the page.

---

**Great! Now you can build interactive web pages by manipulating the DOM with JavaScript.**