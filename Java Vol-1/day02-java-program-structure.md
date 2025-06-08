# Day 2: Java Program Structure

Welcome to Day 2! Today you'll learn about the basic structure of a Java program, how to write comments, and how to compile and run your code.

---

## 1. Java Program Structure

A basic Java program consists of:

- **Class**: The fundamental building block of Java. Every program must have at least one class.
- **Main method**: The starting point of execution.

### Example Structure

```java
public class MyProgram {         // Class declaration
    public static void main(String[] args) { // Main method
        // Statements go here
        System.out.println("Hello from MyProgram!");
    }
}
```

- `public class MyProgram` defines a class named `MyProgram`.
- `public static void main(String[] args)` is the entry point; the JVM looks for this method to start execution.
- Statements (like `System.out.println(...)`) go inside `{ }` of the main method.

---

## 2. Statements in Java

A **statement** is a line of code that performs an action, ending with a semicolon `;`.

Example:
```java
int x = 10;                  // Variable declaration and assignment
System.out.println(x);       // Print statement
```

---

## 3. Comments in Java

Comments are notes in your code ignored by the compiler. They help explain your code to yourself and others.

- **Single-line comment:** starts with `//`
- **Multi-line comment:** enclosed with `/* ... */`

Examples:
```java
// This is a single-line comment

/*
This is a 
multi-line comment
*/
System.out.println("Hello!"); // This prints Hello!
```

---

## 4. Compiling and Running Java Code

Suppose you have a file `MyProgram.java`:

```java
public class MyProgram {
    public static void main(String[] args) {
        System.out.println("Hello from MyProgram!");
    }
}
```

### Step 1: Compile

Open a terminal and run:
```sh
javac MyProgram.java
```
- This produces a `MyProgram.class` file (bytecode).

### Step 2: Run

```sh
java MyProgram
```
- Output will be:
```
Hello from MyProgram!
```

---

## 5. Example: Full Code with Comments

```java
// MyProgram.java
public class MyProgram {
    public static void main(String[] args) {
        // Print a welcome message
        System.out.println("Welcome to Java!");
        
        /* Declare a variable and print its value */
        int year = 2025;
        System.out.println("Year: " + year);
    }
}
```

---

## 🎯 Task Checklist

- [x] Write a Java class with a proper main method.
- [x] Add both single-line and multi-line comments.
- [x] Compile and run your code from the command line.

---

**Awesome! Tomorrow you'll dive into variables and data types in Java.**