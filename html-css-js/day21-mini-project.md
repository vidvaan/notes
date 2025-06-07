# Day 21: Mini Project

Congratulations! Today, you’ll apply your JavaScript skills by building a simple interactive project.  
**Choose one:**  
- A simple **Calculator**  
- A basic **To-Do List**

Below are full examples for both. You can pick one to build, or try both!

---

## Option 1: Simple Calculator

**Features:**  
- Add, subtract, multiply, and divide two numbers.
- Display the result on the page.
- Input validation for numbers.

### `index.html`
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Simple Calculator</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background: #f0f4f8;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
      .calculator {
        background: #fff;
        border-radius: 12px;
        box-shadow: 0 8px 24px rgba(33,150,243,0.10);
        padding: 32px 24px;
        width: 270px;
        text-align: center;
      }
      .calculator input {
        width: 80px;
        padding: 8px;
        margin: 6px 4px;
        border-radius: 4px;
        border: 1.5px solid #c3cfe2;
        font-size: 1.1em;
        text-align: center;
      }
      .calculator button {
        margin: 8px 6px;
        padding: 8px 16px;
        border: none;
        border-radius: 6px;
        background: #2196f3;
        color: #fff;
        font-size: 1.1em;
        cursor: pointer;
        transition: background 0.2s;
      }
      .calculator button:hover {
        background: #1976d2;
      }
      .result {
        margin-top: 16px;
        font-size: 1.25em;
        font-weight: bold;
        color: #1976d2;
      }
    </style>
  </head>
  <body>
    <div class="calculator">
      <h2>Simple Calculator</h2>
      <input type="number" id="num1" placeholder="First number" />
      <input type="number" id="num2" placeholder="Second number" />
      <br />
      <button onclick="calculate('+')">+</button>
      <button onclick="calculate('-')">-</button>
      <button onclick="calculate('*')">&times;</button>
      <button onclick="calculate('/')">&divide;</button>
      <div class="result" id="result"></div>
    </div>
    <script>
      function calculate(op) {
        const n1 = parseFloat(document.getElementById('num1').value);
        const n2 = parseFloat(document.getElementById('num2').value);
        let res = '';
        if (isNaN(n1) || isNaN(n2)) {
          res = "Please enter both numbers.";
        } else {
          switch (op) {
            case '+': res = n1 + n2; break;
            case '-': res = n1 - n2; break;
            case '*': res = n1 * n2; break;
            case '/': 
              res = n2 === 0 ? "Cannot divide by zero" : (n1 / n2); 
              break;
          }
        }
        document.getElementById('result').textContent = res;
      }
    </script>
  </body>
</html>
```

---

## Option 2: To-Do List

**Features:**  
- Add new tasks.
- Mark tasks as done.
- Remove tasks.
- Shows tasks in a list.

### `index.html`
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Simple To-Do List</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background: #e3f2fd;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      .todo-container {
        background: #fff;
        padding: 30px 28px;
        border-radius: 12px;
        box-shadow: 0 6px 24px rgba(33,150,243,0.10);
        width: 320px;
      }
      h2 {
        margin-bottom: 14px;
        color: #2196f3;
      }
      .input-row {
        display: flex;
        gap: 8px;
        margin-bottom: 16px;
      }
      input[type="text"] {
        flex: 1;
        padding: 8px;
        border-radius: 5px;
        border: 1.5px solid #bbdefb;
        font-size: 1em;
      }
      button {
        background: #2196f3;
        color: #fff;
        border: none;
        border-radius: 5px;
        padding: 8px 16px;
        font-size: 1em;
        cursor: pointer;
        transition: background 0.2s;
      }
      button:hover {
        background: #1976d2;
      }
      ul {
        list-style: none;
        padding: 0;
        margin: 0;
      }
      li {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-bottom: 10px;
        padding: 8px 6px;
        border-bottom: 1px solid #f0f0f0;
        border-radius: 4px;
        transition: background 0.2s;
      }
      li.done span {
        text-decoration: line-through;
        color: #90a4ae;
      }
      .actions {
        display: flex;
        gap: 5px;
      }
      .done-btn {
        background: #4caf50;
      }
      .done-btn:hover {
        background: #388e3c;
      }
      .remove-btn {
        background: #e53935;
      }
      .remove-btn:hover {
        background: #b71c1c;
      }
    </style>
  </head>
  <body>
    <div class="todo-container">
      <h2>To-Do List</h2>
      <div class="input-row">
        <input type="text" id="taskInput" placeholder="Add a new task..." />
        <button onclick="addTask()">Add</button>
      </div>
      <ul id="taskList"></ul>
    </div>
    <script>
      function addTask() {
        const input = document.getElementById('taskInput');
        const text = input.value.trim();
        if (!text) return;
        const li = document.createElement('li');
        const span = document.createElement('span');
        span.textContent = text;
        li.appendChild(span);

        const actions = document.createElement('div');
        actions.className = 'actions';

        const doneBtn = document.createElement('button');
        doneBtn.textContent = 'Done';
        doneBtn.className = 'done-btn';
        doneBtn.onclick = function() {
          li.classList.toggle('done');
        };
        actions.appendChild(doneBtn);

        const removeBtn = document.createElement('button');
        removeBtn.textContent = 'Remove';
        removeBtn.className = 'remove-btn';
        removeBtn.onclick = function() {
          li.remove();
        };
        actions.appendChild(removeBtn);

        li.appendChild(actions);
        document.getElementById('taskList').appendChild(li);
        input.value = "";
        input.focus();
      }

      document.getElementById('taskInput').addEventListener('keydown', function(e) {
        if (e.key === 'Enter') addTask();
      });
    </script>
  </body>
</html>
```

---

## 🎯 Task Checklist

- [x] Build either the calculator or the to-do list in a single HTML file.
- [x] Use JavaScript to make your page interactive.
- [x] Style your project using CSS.
- [x] Test all features: add numbers/tasks, perform actions, and see results instantly.

---

**Awesome! You just finished your 3-week HTML, CSS, and JavaScript learning journey with a real project.  
Keep building, experimenting, and learning!**