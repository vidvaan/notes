# Day 20: Functions

Welcome to Day 20! Today you’ll learn how to write and use **functions** in JavaScript. Functions let you organize your code, reuse logic, and keep things clean and manageable.

---

## 1. What is a Function?

A function is a block of code designed to perform a particular task.  
- You **define** a function once, then **call** (execute) it whenever you need.

---

## 2. Defining and Calling Functions

### a. Function Declaration

```javascript
function greet() {
  console.log("Hello, world!");
}
```

**Calling a function:**

```javascript
greet(); // Outputs: Hello, world!
```

---

### b. Function with Parameters

Parameters allow you to pass information into your function.

```javascript
function greetUser(name) {
  console.log("Hello, " + name + "!");
}

greetUser("Alice"); // Outputs: Hello, Alice!
```

You can use multiple parameters:

```javascript
function add(a, b) {
  console.log(a + b);
}

add(3, 5); // Outputs: 8
```

---

### c. Returning a Value

Use `return` to send a value back from the function.

```javascript
function multiply(x, y) {
  return x * y;
}

let result = multiply(4, 6); // result = 24
console.log(result);
```

---

### d. Function Expressions

You can also define functions as expressions and assign them to variables:

```javascript
const sayHi = function(name) {
  return "Hi, " + name;
};

console.log(sayHi("Bob"));
```

---

### e. Arrow Functions

Introduced in ES6 (2015), arrow functions are a shorter way to write functions.

```javascript
// Regular function
function square(n) {
  return n * n;
}

// Arrow function
const squareArrow = (n) => {
  return n * n;
};

// Shortest form for single-expression functions:
const squareShort = n => n * n;

console.log(squareArrow(5));   // 25
console.log(squareShort(6));   // 36
```

---

## 3. Example: Functions in Action

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Functions Example</title>
  </head>
  <body>
    <h1>Open your console to see function outputs!</h1>
    <script>
      // Function declaration
      function greet() {
        console.log("Hello, world!");
      }
      greet();

      // Function with parameter
      function greetUser(name) {
        console.log("Hello, " + name + "!");
      }
      greetUser("Vidvaan");

      // Function with return value
      function add(a, b) {
        return a + b;
      }
      let sum = add(7, 8);
      console.log("Sum:", sum);

      // Arrow function
      const multiply = (x, y) => x * y;
      console.log("Product:", multiply(4, 5));
    </script>
  </body>
</html>
```

---

## 4. Best Practices

- Use descriptive names for functions and parameters.
- Prefer `const` for function expressions and arrow functions unless you need to reassign.
- Use arrow functions for short, simple functions, especially as callbacks.
- Functions should do one thing (single responsibility).

---

## 🎯 Task Checklist

- [x] Write and call a function that prints a message.
- [x] Write a function with parameters and call it with different arguments.
- [x] Write a function that returns a value and use that value.
- [x] Write an arrow function.

---

**Great job! Next, you’ll learn about JavaScript scope and how variables behave inside and outside functions.**