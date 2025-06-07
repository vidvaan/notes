# Day 16: Variables & Data Types

Welcome to Day 16! Today, you'll learn about **variables** (how to store data in JavaScript) and the main **data types** you'll use in your programs.

---

## 1. Declaring Variables: `var`, `let`, and `const`

Variables are containers for storing data values.

### a. `var`

- Oldest way to declare variables.
- Function-scoped.
- Can be re-declared and updated.

```javascript
var name = "Alice";
var name = "Bob"; // No error
```

### b. `let`

- Introduced in ES6 (2015).
- Block-scoped.
- Can be updated, but **not** re-declared within the same scope.

```javascript
let age = 25;
age = 26; // OK
// let age = 27; // Error: already declared in this scope
```

### c. `const`

- Also block-scoped.
- Must be assigned a value at declaration.
- Cannot be updated or re-declared.

```javascript
const PI = 3.14159;
// PI = 3.14; // Error!
```

**Summary Table:**

| Keyword | Scope   | Can re-declare? | Can update? |
|---------|---------|-----------------|-------------|
| var     | function| Yes             | Yes         |
| let     | block   | No              | Yes         |
| const   | block   | No              | No          |

---

## 2. Data Types in JavaScript

JavaScript is a **dynamically typed** language: variables can hold any type, and types can change.

### a. Numbers

Store numeric values (integers or floats).

```javascript
let x = 42;
let y = 3.14;
```

### b. Strings

Store text, wrapped in single `'`, double `"`, or backticks `` ` ``.

```javascript
let name = "Jane";
let greeting = 'Hello, world!';
let message = `Hi, ${name}!`; // Template literal
```

### c. Booleans

Store `true` or `false` values.

```javascript
let isActive = true;
let isComplete = false;
```

### d. Arrays

Ordered lists of values (can mix types).

```javascript
let colors = ["red", "green", "blue"];
let numbers = [1, 2, 3, 4, 5];
let mixed = [1, "two", true, [3, 4]];
```

Access elements by index (starting at 0):

```javascript
console.log(colors[0]); // "red"
```

### e. Objects

Collections of key-value pairs (like dictionaries).

```javascript
let person = {
  name: "Alice",
  age: 30,
  isStudent: false
};

console.log(person.name); // "Alice"
console.log(person["age"]); // 30
```

Objects can also contain arrays and other objects.

---

## 3. Example: All Variable Types

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Variables & Data Types Example</title>
  </head>
  <body>
    <script>
      // var, let, const
      var language = "JavaScript";
      let version = 2025;
      const creator = "Brendan Eich";

      // Numbers
      let score = 99.5;

      // Strings
      let message = "Welcome to JS!";
      let user = 'vidvaan';
      let greeting = `Hello, ${user}!`;

      // Booleans
      let isAdmin = false;
      let isLoggedIn = true;

      // Arrays
      let fruits = ["apple", "banana", "cherry"];

      // Objects
      let car = {
        brand: "Toyota",
        model: "Corolla",
        year: 2022
      };

      // Output
      console.log(language, version, creator);
      console.log(score, message, greeting);
      console.log(isAdmin, isLoggedIn);
      console.log(fruits[1]); // "banana"
      console.log(car.brand); // "Toyota"
    </script>
    <h1>Open your browser's console to see the output!</h1>
  </body>
</html>
```

---

## 4. Best Practices

- Use `let` and `const` (prefer `const` by default).
- Use `let` only when you need to reassign.
- Use descriptive variable names.
- Remember arrays and objects are reference types—`const` prevents reassignment, but their contents can change.

```javascript
const user = { name: "Alex" };
user.name = "Jordan"; // OK
// user = {}; // Error
```

---

## 🎯 Task Checklist

- [x] Declare variables using `var`, `let`, and `const`
- [x] Store and use numbers, strings, and booleans
- [x] Create and access arrays
- [x] Create and access objects

---

**Great job! Next, you’ll learn about operators and basic expressions in JavaScript.**