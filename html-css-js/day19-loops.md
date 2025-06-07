# Day 19: Loops

Welcome to Day 19! Today, you’ll learn how to repeat actions and process collections in JavaScript using **loops**. Loops are fundamental for automating repetitive tasks in programming.

---

## 1. Why Use Loops?

Loops let you run the same block of code multiple times, often with different values. This is useful for iterating through arrays, processing user input, or performing actions until a certain condition is met.

---

## 2. Types of Loops in JavaScript

### a. `for` Loop

The most common loop for running code a specific number of times.

```javascript
for (initialization; condition; increment) {
  // code to run each time
}
```

**Example: Print numbers 1 to 5**
```javascript
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

---

### b. `while` Loop

Repeats as long as a condition is true.  
Check the condition **before** each loop.

```javascript
while (condition) {
  // code to run
}
```

**Example:**
```javascript
let n = 1;
while (n <= 5) {
  console.log(n);
  n++;
}
```

---

### c. `do-while` Loop

Like `while`, but checks the condition **after** running the code block at least once.

```javascript
do {
  // code to run
} while (condition);
```

**Example:**
```javascript
let x = 1;
do {
  console.log(x);
  x++;
} while (x <= 5);
```

---

## 3. Loop Control: `break` and `continue`

- **`break`**: Immediately exits the loop.
- **`continue`**: Skips the rest of the current iteration and moves to the next.

**Example: Using `break`**
```javascript
for (let i = 1; i <= 10; i++) {
  if (i === 6) break;
  console.log(i); // Prints 1 to 5
}
```

**Example: Using `continue`**
```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i); // Prints 1, 2, 4, 5 (skips 3)
}
```

---

## 4. Full Example: Loops in Action

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Loops Example</title>
  </head>
  <body>
    <h1>Check the Console for Loop Outputs!</h1>
    <script>
      // for loop
      for (let i = 1; i <= 5; i++) {
        console.log("for loop: " + i);
      }

      // while loop
      let n = 1;
      while (n <= 3) {
        console.log("while loop: " + n);
        n++;
      }

      // do-while loop
      let x = 1;
      do {
        console.log("do-while loop: " + x);
        x++;
      } while (x <= 2);

      // break
      for (let i = 1; i <= 5; i++) {
        if (i === 4) break;
        console.log("break example: " + i);
      }

      // continue
      for (let i = 1; i <= 5; i++) {
        if (i === 2) continue;
        console.log("continue example: " + i);
      }
    </script>
  </body>
</html>
```

---

## 5. Best Practices

- Use `for` loops when you know how many times you want to repeat.
- Use `while` or `do-while` when the number of repetitions depends on a condition.
- Use `break` and `continue` for finer control, but avoid overusing them.
- Avoid infinite loops (make sure your loop condition will eventually be false).

---

## 🎯 Task Checklist

- [x] Print numbers 1 to 5 using a `for` loop.
- [x] Print numbers 1 to 5 using a `while` loop.
- [x] Print numbers 1 to 5 using a `do-while` loop.
- [x] Use `break` to exit a loop early.
- [x] Use `continue` to skip an iteration.

---

**Great job! Next, you’ll learn about functions in JavaScript for organizing reusable code.**