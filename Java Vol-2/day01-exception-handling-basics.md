# Day 1: Exception Handling Basics

## What is an Exception?

An **exception** is an event that disrupts the normal flow of a program’s execution. It occurs during the execution of a program and signals that an error or an unexpected event has happened, which must be handled to prevent the program from crashing.

---

## Checked vs. Unchecked Exceptions

- **Checked Exceptions:**
  - Checked at compile-time.
  - Must be either caught or declared to be thrown.
  - Examples: `IOException`, `SQLException`.
  - If not handled, the code will not compile.

- **Unchecked Exceptions:**
  - Checked at runtime (not at compile-time).
  - Inherit from `RuntimeException`.
  - Examples: `NullPointerException`, `ArrayIndexOutOfBoundsException`.
  - If not handled, the program may terminate abruptly.

---

## Exception Hierarchy

```
Throwable
  ├── Error (serious issues, usually not handled by programs)
  └── Exception
        ├── Checked Exceptions (IOException, SQLException, etc.)
        └── Unchecked Exceptions (RuntimeException and its subclasses)
```

---

## Basic try-catch-finally

The `try-catch-finally` block is used to handle exceptions and ensure certain code runs regardless of whether an exception occurs.

**Syntax Example:**

```java
try {
    // Code that may throw an exception
    int result = 10 / 0;
} catch (ArithmeticException e) {
    // Code to handle the exception
    System.out.println("Cannot divide by zero: " + e.getMessage());
} finally {
    // Code that always executes
    System.out.println("Finally block executed.");
}
```

- **try:** Wraps code that might throw an exception.
- **catch:** Handles the specific exception type.
- **finally:** Executes whether or not an exception was thrown.

---

**Practice:**
- Write a small program that divides two numbers and handles division by zero using try-catch-finally.
- Experiment by throwing both checked and unchecked exceptions.

---