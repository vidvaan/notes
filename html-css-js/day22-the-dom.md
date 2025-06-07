# Day 22: The DOM

Welcome to Day 22! Today you'll learn about the **DOM** (Document Object Model) and how to use JavaScript to select and manipulate elements on your web page.

---

## 1. What is the DOM?

The **DOM** is a programming interface for HTML and XML documents.  
- It represents your web page as a **tree of objects** (nodes), where each element, attribute, and piece of text is a node.
- JavaScript uses the DOM to read, change, add, or remove parts of your web page.

**Example:**  
This HTML:

```html
<body>
  <h1>Hello!</h1>
  <p>Welcome to the DOM.</p>
</body>
```

Becomes this DOM tree:

```
Document
└── html
    └── body
        ├── h1
        └── p
```

---

## 2. Selecting Elements in the DOM

To change or read elements using JavaScript, you first need to select them.  
Here are the most common ways:

---

### a. `getElementById`

Selects a single element with a specific `id` attribute.

```html
<p id="greet">Hello!</p>
```

```javascript
let el = document.getElementById('greet');
console.log(el.textContent); // "Hello!"
```

---

### b. `getElementsByClassName`

Selects all elements with a given class. Returns an **HTMLCollection** (like an array).

```html
<ul>
  <li class="item">A</li>
  <li class="item">B</li>
</ul>
```

```javascript
let items = document.getElementsByClassName('item');
console.log(items[0].textContent); // "A"
```

---

### c. `getElementsByTagName`

Selects all elements with a specific tag name.

```javascript
let ps = document.getElementsByTagName('p');
console.log(ps.length); // Number of <p> elements
```

---

### d. `querySelector`

Selects **the first** element that matches a CSS selector.

```html
<p class="note">Hi!</p>
```

```javascript
let note = document.querySelector('.note');
console.log(note.textContent); // "Hi!"
```

---

### e. `querySelectorAll`

Selects **all** elements that match a CSS selector. Returns a **NodeList**.

```html
<ul>
  <li class="item">1</li>
  <li class="item">2</li>
</ul>
```

```javascript
let allItems = document.querySelectorAll('.item');
allItems.forEach(function(item) {
  console.log(item.textContent); // "1" and then "2"
});
```

---

## 3. Example: Selecting Elements

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Selection Example</title>
  </head>
  <body>
    <h1 id="main-heading">DOM Example</h1>
    <p class="desc">Welcome to the DOM!</p>
    <p class="desc">Learn JavaScript DOM methods.</p>
    <ul>
      <li class="item">Apple</li>
      <li class="item">Banana</li>
    </ul>
    <script>
      // By ID
      const heading = document.getElementById('main-heading');
      console.log(heading.textContent);

      // By class
      const descs = document.getElementsByClassName('desc');
      console.log(descs[0].textContent);

      // By tag name
      const paragraphs = document.getElementsByTagName('p');
      console.log(paragraphs.length);

      // querySelector (first match)
      const firstItem = document.querySelector('.item');
      console.log(firstItem.textContent);

      // querySelectorAll (all matches)
      const items = document.querySelectorAll('.item');
      items.forEach(item => console.log(item.textContent));
    </script>
  </body>
</html>
```

---

## 4. Best Practices

- Use `getElementById` for unique elements.
- Use `querySelector`/`querySelectorAll` for more flexible, CSS-like selection.
- Use `forEach` with `querySelectorAll` for easy looping.

---

## 🎯 Task Checklist

- [x] Select elements by ID, class, tag, and CSS selector.
- [x] Log their text or content to the console.
- [x] Try changing an element’s text using `.textContent`.

---

**Great! Next, you’ll learn how to change and manipulate DOM elements with JavaScript.**