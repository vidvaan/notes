# Day 4: Operators

Welcome to Day 4! Today you'll learn about the different types of operators in Java and how they are used to perform calculations, comparisons, and logical operations.

---

## 1. Arithmetic Operators

Used for mathematical calculations.

| Operator | Description        | Example         | Result   |
|----------|-------------------|-----------------|----------|
| +        | Addition          | `5 + 2`         | `7`      |
| -        | Subtraction       | `5 - 2`         | `3`      |
| *        | Multiplication    | `5 * 2`         | `10`     |
| /        | Division          | `5 / 2`         | `2`      |
| %        | Modulus (remainder) | `5 % 2`      | `1`      |

**Example:**
```java
int a = 10, b = 3;
System.out.println(a + b); // 13
System.out.println(a - b); // 7
System.out.println(a * b); // 30
System.out.println(a / b); // 3 (integer division)
System.out.println(a % b); // 1
```

---

## 2. Assignment Operators

Used to assign values to variables.

| Operator | Example     | Equivalent to   |
|----------|-------------|----------------|
| =        | a = 5       | a = 5          |
| +=       | a += 2      | a = a + 2      |
| -=       | a -= 2      | a = a - 2      |
| *=       | a *= 2      | a = a * 2      |
| /=       | a /= 2      | a = a / 2      |
| %=       | a %= 2      | a = a % 2      |

---

## 3. Relational Operators

Used to compare two values (result is boolean: `true` or `false`).

| Operator | Description     | Example      | Result    |
|----------|----------------|-------------|-----------|
| ==       | Equal to       | `a == b`    | false     |
| !=       | Not equal to   | `a != b`    | true      |
| >        | Greater than   | `a > b`     | true      |
| <        | Less than      | `a < b`     | false     |
| >=       | Greater or equal | `a >= b`  | true      |
| <=       | Less or equal    | `a <= b`  | false     |

**Example:**
```java
int a = 5, b = 3;
System.out.println(a > b);  // true
System.out.println(a == b); // false
```

---

## 4. Logical Operators

Used to combine multiple boolean expressions.

| Operator | Description          | Example           | Result        |
|----------|---------------------|-------------------|---------------|
| &&       | Logical AND         | `true && false`   | false         |
| \|\|     | Logical OR          | `true || false`   | true          |
| !        | Logical NOT         | `!true`           | false         |

**Example:**
```java
int age = 20;
boolean isStudent = true;
System.out.println(age > 18 && isStudent); // true
System.out.println(age > 18 || isStudent); // true
System.out.println(!(age > 18));           // false
```

---

## 5. Increment and Decrement Operators

Used to increase or decrease a value by 1.

| Operator | Description        | Example    | Result      |
|----------|-------------------|------------|-------------|
| ++       | Increment         | `a++`      | a = a + 1   |
| --       | Decrement         | `a--`      | a = a - 1   |

**Pre and Post forms:**
- `++a` (pre-increment): Increments, then uses the value.
- `a++` (post-increment): Uses the value, then increments.

**Example:**
```java
int a = 5;
System.out.println(++a); // 6 (increment, then print)
System.out.println(a++); // 6 (print, then increment)
System.out.println(a);   // 7
```

---

## 6. Ternary Operator

A shorthand for simple if-else statements.

**Syntax:**  
`result = (condition) ? valueIfTrue : valueIfFalse;`

**Example:**
```java
int a = 10, b = 20;
int max = (a > b) ? a : b; // max will be 20
System.out.println("Max: " + max);
```

---

## 7. Full Example

```java
public class OperatorDemo {
    public static void main(String[] args) {
        int x = 7, y = 3;
        System.out.println("x + y = " + (x + y));
        System.out.println("x > y: " + (x > y));
        System.out.println("x == y: " + (x == y));

        x += 2; // x = x + 2
        System.out.println("x after += 2: " + x);

        boolean result = (x > 10) && (y < 5);
        System.out.println("Logical AND result: " + result);

        int min = (x < y) ? x : y;
        System.out.println("Min value: " + min);
    }
}
```

---

## 🎯 Task Checklist

- [x] Practice arithmetic, assignment, relational, and logical operators.
- [x] Use increment/decrement and ternary operator in examples.
- [x] Write a Java program demonstrating multiple operators.

---

**Awesome! Tomorrow you'll learn about user input and output in Java.**