# Day 17: Operators & Expressions

Welcome to Day 17! Today, you'll learn how to perform calculations and make decisions in JavaScript using **operators** and **expressions**.

---

## 1. What is an Expression?

An **expression** is any valid unit of code that resolves to a value.  
Examples:  
- `5 + 3`
- `"Hello, " + name`
- `x > 10`

---

## 2. Operators in JavaScript

Operators allow you to perform operations on values and variables. There are several types:

---

### a. Arithmetic Operators

Used for numeric calculations.

| Operator | Description      | Example      | Result         |
|----------|------------------|-------------|---------------|
| `+`      | Addition         | `5 + 2`     | `7`           |
| `-`      | Subtraction      | `5 - 2`     | `3`           |
| `*`      | Multiplication   | `5 * 2`     | `10`          |
| `/`      | Division         | `5 / 2`     | `2.5`         |
| `%`      | Modulus (Remainder) | `5 % 2` | `1`           |
| `**`     | Exponentiation   | `5 ** 2`    | `25`          |
| `++`     | Increment        | `x++`       | `x = x + 1`   |
| `--`     | Decrement        | `x--`       | `x = x - 1`   |

---

### b. Assignment Operators

Used to assign values to variables.

| Operator | Example    | Same As      |
|----------|------------|--------------|
| `=`      | `x = 5`    | `x = 5`      |
| `+=`     | `x += 2`   | `x = x + 2`  |
| `-=`     | `x -= 2`   | `x = x - 2`  |
| `*=`     | `x *= 2`   | `x = x * 2`  |
| `/=`     | `x /= 2`   | `x = x / 2`  |
| `%=`     | `x %= 2`   | `x = x % 2`  |
| `**=`    | `x **= 2`  | `x = x ** 2` |

---

### c. Comparison Operators

Used to compare two values and return a boolean (`true` or `false`).

| Operator | Description           | Example      | Result      |
|----------|-----------------------|--------------|-------------|
| `==`     | Equal to (loose)      | `5 == '5'`   | `true`      |
| `===`    | Equal value & type    | `5 === '5'`  | `false`     |
| `!=`     | Not equal (loose)     | `5 != '5'`   | `false`     |
| `!==`    | Not equal value/type  | `5 !== '5'`  | `true`      |
| `>`      | Greater than          | `7 > 5`      | `true`      |
| `<`      | Less than             | `7 < 5`      | `false`     |
| `>=`     | Greater than or equal | `5 >= 5`     | `true`      |
| `<=`     | Less than or equal    | `4 <= 5`     | `true`      |

---

### d. Logical Operators

Used to combine or invert boolean values.

| Operator | Description    | Example          | Result      |
|----------|----------------|------------------|-------------|
| `&&`     | AND            | `true && false`  | `false`     |
| `||`     | OR             | `true || false`  | `true`      |
| `!`      | NOT            | `!true`          | `false`     |

---

## 3. Example Programs

### Example 1: Arithmetic Operations

```javascript
let a = 10, b = 3;
console.log("a + b =", a + b);   // 13
console.log("a - b =", a - b);   // 7
console.log("a * b =", a * b);   // 30
console.log("a / b =", a / b);   // 3.333...
console.log("a % b =", a % b);   // 1
console.log("a ** b =", a ** b); // 1000
```

---

### Example 2: Assignment and Increment/Decrement

```javascript
let x = 5;
x += 2;   // x = 7
x++;      // x = 8
x *= 3;   // x = 24
console.log(x); // 24
```

---

### Example 3: Comparisons

```javascript
let n = 20;
console.log(n > 10);    // true
console.log(n == "20"); // true (loose equality)
console.log(n === "20");// false (strict equality)
console.log(n != 15);   // true
```

---

### Example 4: Logical Operators

```javascript
let score = 85;
let passed = score >= 50;
let perfect = score === 100;

console.log(passed && !perfect); // true (passed, but not perfect)
console.log(passed || perfect);  // true (at least one is true)
```

---

### Example 5: Combine All in a Mini Program

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JS Operators Example</title>
  </head>
  <body>
    <h1>Open the console for output</h1>
    <script>
      // Arithmetic
      let a = 7, b = 2;
      console.log("a + b =", a + b);

      // Assignment
      let x = 10;
      x -= 3;
      console.log("x after -= 3:", x);

      // Comparison
      let age = 18;
      if (age >= 18) {
        console.log("Adult");
      } else {
        console.log("Minor");
      }

      // Logical
      let hasID = true, isOver18 = false;
      if (hasID && isOver18) {
        console.log("Entry allowed");
      } else {
        console.log("Entry denied");
      }
    </script>
  </body>
</html>
```

---

## 4. Best Practices

- Use `===` and `!==` for comparison to avoid type coercion issues.
- Use parentheses `()` to clarify order of operations.
- Use meaningful variable names.

---

## 🎯 Task Checklist

- [x] Use arithmetic operators to perform calculations.
- [x] Assign and update values using assignment operators.
- [x] Compare values with comparison operators.
- [x] Combine conditions with logical operators.

---

**Awesome! Next, you’ll learn about conditional statements to control your program’s flow.**