# Day 18: Control Flow in JavaScript

Welcome to Day 18! Today, you'll learn how to make your JavaScript code make decisions using **conditional statements**: `if`, `else if`, `else`, and `switch`. These tools allow your code to react to different situations and inputs.

---

## 1. The `if` Statement

The `if` statement lets your code execute a block only if a condition is true.

```javascript
if (condition) {
  // code runs if condition is true
}
```

**Example:**

```javascript
let age = 20;

if (age >= 18) {
  console.log("You are an adult.");
}
```

---

## 2. The `else` Statement

Use `else` to run code if the `if` condition is **not** true.

```javascript
if (condition) {
  // if true
} else {
  // if false
}
```

**Example:**

```javascript
let hour = 16;

if (hour < 12) {
  console.log("Good morning!");
} else {
  console.log("Good afternoon!");
}
```

---

## 3. The `else if` Statement

Use `else if` to test multiple conditions in sequence.

```javascript
if (condition1) {
  // if condition1 is true
} else if (condition2) {
  // if condition2 is true
} else {
  // if none are true
}
```

**Example:**

```javascript
let score = 78;

if (score >= 90) {
  console.log("Grade: A");
} else if (score >= 80) {
  console.log("Grade: B");
} else if (score >= 70) {
  console.log("Grade: C");
} else {
  console.log("Grade: D or below");
}
```

---

## 4. The `switch` Statement

The `switch` statement is useful for checking a variable against many possible values.

```javascript
switch (expression) {
  case value1:
    // code for value1
    break;
  case value2:
    // code for value2
    break;
  default:
    // code if no case matches
}
```

**Example:**

```javascript
let fruit = "apple";

switch (fruit) {
  case "banana":
    console.log("Yellow fruit!");
    break;
  case "apple":
    console.log("Red or green fruit!");
    break;
  case "orange":
    console.log("Orange fruit!");
    break;
  default:
    console.log("Unknown fruit.");
}
```

---

## 5. Full Example: Control Flow in Action

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Control Flow Example</title>
  </head>
  <body>
    <h1>Open your console to see the output!</h1>
    <script>
      // if, else if, else
      let temp = 35;

      if (temp > 40) {
        console.log("It's very hot!");
      } else if (temp > 25) {
        console.log("It's warm.");
      } else if (temp > 15) {
        console.log("It's cool.");
      } else {
        console.log("It's cold.");
      }

      // switch
      let day = 3;
      let dayName;
      switch (day) {
        case 1:
          dayName = "Monday";
          break;
        case 2:
          dayName = "Tuesday";
          break;
        case 3:
          dayName = "Wednesday";
          break;
        case 4:
          dayName = "Thursday";
          break;
        case 5:
          dayName = "Friday";
          break;
        default:
          dayName = "Weekend";
      }
      console.log("Today is " + dayName);
    </script>
  </body>
</html>
```

---

## 6. Best Practices

- Use `if/else if/else` for ranges or complex boolean logic.
- Use `switch` for comparing the same variable against many specific values.
- Always include a `default` case in `switch` for unexpected values.
- Use `break;` in each `case` to prevent "fall-through" bugs.

---

## 🎯 Task Checklist

- [x] Use `if`, `else if`, and `else` to handle multiple conditions.
- [x] Try a `switch` statement for value-based decisions.
- [x] Test your code by changing variable values.

---

**Awesome! Next, you'll learn about loops to repeat actions in your JavaScript programs.**