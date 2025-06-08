# Day 6: Control Flow – If/Else and Switch

Welcome to Day 6! Today you'll learn how to control the flow of your Java programs using `if`, `else if`, `else` statements, and the `switch-case` structure.

---

## 1. if, else if, else Statements

These statements let you execute different code blocks based on conditions.

**Basic Syntax:**
```java
if (condition) {
    // Code if condition is true
} else if (anotherCondition) {
    // Code if anotherCondition is true
} else {
    // Code if none of the above are true
}
```

### Example:
```java
int num = 10;
if (num > 0) {
    System.out.println("Positive number");
} else if (num < 0) {
    System.out.println("Negative number");
} else {
    System.out.println("Zero");
}
```

---

## 2. Nested if Statements

You can put one if inside another for more complex decisions.

```java
int age = 20;
if (age >= 18) {
    if (age < 60) {
        System.out.println("Adult");
    } else {
        System.out.println("Senior");
    }
} else {
    System.out.println("Minor");
}
```

---

## 3. switch-case Statements

The `switch` statement is useful when you have multiple possible values for a variable and want to execute different code for each.

**Basic Syntax:**
```java
switch (variable) {
    case value1:
        // Code for value1
        break;
    case value2:
        // Code for value2
        break;
    // ... more cases ...
    default:
        // Code if no cases match
}
```

- `break` exits the switch after a match. Without it, execution "falls through" to the next case.
- `default` is optional; runs if no case matches.

### Example:
```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Another day");
}
```
_Output:_  
```
Wednesday
```

---

## 4. Example: Grading System

```java
char grade = 'B';

switch (grade) {
    case 'A':
        System.out.println("Excellent!");
        break;
    case 'B':
        System.out.println("Well done");
        break;
    case 'C':
        System.out.println("Good");
        break;
    case 'D':
        System.out.println("You passed");
        break;
    case 'F':
        System.out.println("Better try again");
        break;
    default:
        System.out.println("Invalid grade");
}
```

---

## 5. When to Use Which?

- Use `if-else` for ranges or complex conditions.
- Use `switch-case` for multiple specific discrete values.

---

## 🎯 Task Checklist

- [x] Use `if`, `else if`, and `else` in a Java program.
- [x] Use `switch-case` in a Java program.
- [x] Write a simple program that takes a number (1–7) and prints the day of the week using both `if-else` and `switch`.

---

**Great work! Tomorrow you'll learn about loops in Java.**