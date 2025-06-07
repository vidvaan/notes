# Day 27: Local Storage & JSON

Welcome to Day 27! Today you'll learn how to **save data in the browser** using `localStorage`, and how to use **JSON** to store and retrieve complex data like arrays and objects.

---

## 1. What is localStorage?

- `localStorage` is a built-in browser feature for storing small amounts of data **persistently** (even after closing the browser).
- Data is stored as **key-value pairs**, and both key and value must be strings.

---

### a. Storing Data

```javascript
localStorage.setItem("username", "vidvaan");
```

### b. Retrieving Data

```javascript
let name = localStorage.getItem("username");
console.log(name); // "vidvaan"
```

### c. Removing Data

```javascript
localStorage.removeItem("username");
```

### d. Clearing All Data

```javascript
localStorage.clear();
```

---

## 2. Storing Complex Data with JSON

Because `localStorage` only stores strings, you need to **convert (serialize) objects and arrays to strings** using `JSON.stringify()` before saving, and **convert them back (parse)** with `JSON.parse()` when reading.

### a. Store an Array

```javascript
let tasks = ["Buy milk", "Learn JS"];
localStorage.setItem("tasks", JSON.stringify(tasks));
```

### b. Retrieve an Array

```javascript
let savedTasks = JSON.parse(localStorage.getItem("tasks"));
console.log(savedTasks); // ["Buy milk", "Learn JS"]
```

### c. Store an Object

```javascript
let user = { name: "Vidvaan", age: 20 };
localStorage.setItem("user", JSON.stringify(user));
```

### d. Retrieve an Object

```javascript
let savedUser = JSON.parse(localStorage.getItem("user"));
console.log(savedUser.name); // "Vidvaan"
```

---

## 3. Example: Simple To-Do List with localStorage

```html
<!DOCTYPE html>
<html>
  <head>
    <title>To-Do List with localStorage</title>
    <style>
      body { font-family: Arial, sans-serif; }
      input { padding: 6px; }
      button { padding: 6px 12px; }
      ul { margin-top: 12px; }
      li { margin-bottom: 7px; }
    </style>
  </head>
  <body>
    <h2>To-Do List</h2>
    <input id="taskInput" type="text" placeholder="New task..." />
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
    <script>
      // Load tasks from localStorage
      let tasks = JSON.parse(localStorage.getItem("myTasks")) || [];
      function renderTasks() {
        const list = document.getElementById("taskList");
        list.innerHTML = "";
        tasks.forEach((task, index) => {
          const li = document.createElement("li");
          li.textContent = task;
          const btn = document.createElement("button");
          btn.textContent = "Remove";
          btn.onclick = function() {
            tasks.splice(index, 1);
            localStorage.setItem("myTasks", JSON.stringify(tasks));
            renderTasks();
          };
          li.appendChild(btn);
          list.appendChild(li);
        });
      }
      function addTask() {
        const input = document.getElementById("taskInput");
        const value = input.value.trim();
        if (value) {
          tasks.push(value);
          localStorage.setItem("myTasks", JSON.stringify(tasks));
          renderTasks();
          input.value = "";
        }
      }
      renderTasks();
    </script>
  </body>
</html>
```

---

## 4. Best Practices

- Always use `JSON.stringify()` when saving arrays/objects, and `JSON.parse()` when reading them.
- Check for `null` when retrieving from localStorage (if the key does not exist).
- Use unique keys to avoid overwriting unrelated data.
- Remember that localStorage is **per domain** and has storage limits (typically ~5MB).

---

## 🎯 Task Checklist

- [x] Store and retrieve simple strings in `localStorage`.
- [x] Store and retrieve arrays or objects using `JSON.stringify`/`JSON.parse`.
- [x] Build a mini project that saves user data between page reloads.

---

**Awesome! Now you can store user data persistently in the browser and handle JSON like a pro.**