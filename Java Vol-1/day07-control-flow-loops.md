# Day 7: Control Flow – Loops

Welcome to Day 7! Today, you'll learn how to repeat actions in Java using loops: `for`, `while`, and `do-while`. You'll also see how `break` and `continue` affect loop flow.

---

## 1. The `for` Loop

Use a `for` loop when you know **how many times** you want to repeat something.

**Syntax:**
```java
for (initialization; condition; update) {
    // Code to repeat
}
```

**Example:**
```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Count: " + i);
}
```

_Output:_
```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

---

## 2. The `while` Loop

Use a `while` loop when you want to repeat **as long as a condition is true**.

**Syntax:**
```java
while (condition) {
    // Code to repeat
}
```

**Example:**
```java
int n = 1;
while (n <= 5) {
    System.out.println("Number: " + n);
    n++;
}
```

---

## 3. The `do-while` Loop

A `do-while` loop always runs **at least once**, then checks the condition.

**Syntax:**
```java
do {
    // Code to repeat
} while (condition);
```

**Example:**
```java
int num = 1;
do {
    System.out.println("Num: " + num);
    num++;
} while (num <= 5);
```

---

## 4. `break` and `continue`

- **`break`**: Exits the loop immediately.
- **`continue`**: Skips the rest of the current iteration and moves to the next loop cycle.

**Example with `break` and `continue`:**
```java
for (int i = 1; i <= 10; i++) {
    if (i == 6) break;           // Stop the loop when i is 6
    if (i % 2 == 0) continue;    // Skip even numbers
    System.out.println(i);       // Prints only odd numbers 1, 3, 5
}
```

---

## 5. Example: Sum of Numbers

```java
public class LoopDemo {
    public static void main(String[] args) {
        int sum = 0;
        for (int i = 1; i <= 100; i++) {
            sum += i;
        }
        System.out.println("Sum of 1 to 100 is " + sum);
    }
}
```

---

## 6. Practice: Multiplication Table

```java
int n = 5;
for (int i = 1; i <= 10; i++) {
    System.out.println(n + " x " + i + " = " + (n * i));
}
```

---

## 🎯 Task Checklist

- [x] Practice all three loops: `for`, `while`, and `do-while`.
- [x] Use `break` and `continue` in a loop.
- [x] Write a program to print all odd numbers from 1 to 20 using a loop.

---

**Great job! Next, you'll learn about arrays in Java.**