# Day 19: Exception Handling

Welcome to Day 19! Today you'll learn about **exception handling** in Java—how to detect and handle errors gracefully, understand exception types and hierarchy, use try-catch-finally, throw/throws, and create custom exceptions.

---

## 1. What is an Exception?

- An **exception** is an event that disrupts the normal flow of a program (usually an error).
- Exception handling lets you catch and deal with errors without crashing your application.

---

## 2. Exception Types and Hierarchy

Java exceptions are objects. The basic hierarchy is:

```
java.lang.Object
    └── java.lang.Throwable
        ├── java.lang.Error        (serious errors, usually not handled)
        └── java.lang.Exception    (can/should be handled)
            ├── java.lang.RuntimeException (unchecked)
            └── (other checked exceptions)
```

### - **Checked exceptions**: Must be caught or declared (e.g., `IOException`, `SQLException`)
### - **Unchecked exceptions**: Not mandatory to catch (e.g., `ArithmeticException`, `NullPointerException`)

---

## 3. try-catch-finally

**Basic syntax:**
```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Handle exception
} finally {
    // (Optional) Always runs, even if exception occurs
}
```

**Example:**
```java
public class TryCatchDemo {
    public static void main(String[] args) {
        try {
            int x = 5 / 0;  // Will throw ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            System.out.println("Finally block always runs.");
        }
    }
}
```

_Output:_
```
Error: / by zero
Finally block always runs.
```

---

## 4. throw and throws

- **throw**: Used to explicitly throw an exception.
- **throws**: Used in method signature to declare that a method might throw exceptions (for checked exceptions).

**Example using throw:**
```java
public class ThrowDemo {
    public static void main(String[] args) {
        int age = -5;
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative");
        }
    }
}
```

**Example using throws:**
```java
import java.io.*;

public class ThrowsDemo {
    public static void main(String[] args) throws IOException {
        readFile();
    }
    static void readFile() throws IOException {
        FileReader fr = new FileReader("test.txt");
        fr.close();
    }
}
```

---

## 5. Custom Exceptions

You can create your own exception classes by extending `Exception` or `RuntimeException`.

**Example:**
```java
class MyException extends Exception {
    public MyException(String message) {
        super(message);
    }
}

public class CustomExceptionDemo {
    public static void main(String[] args) {
        try {
            validate(15);
        } catch (MyException e) {
            System.out.println("Caught: " + e.getMessage());
        }
    }
    static void validate(int age) throws MyException {
        if (age < 18)
            throw new MyException("Not eligible (age < 18)");
        System.out.println("Eligible");
    }
}
```

---

## 6. Multiple Catch Blocks

Handle different exception types separately:
```java
try {
    int[] arr = new int[3];
    System.out.println(arr[4]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array error!");
} catch (Exception e) {
    System.out.println("Other error!");
}
```

---

## 🎯 Task Checklist

- [x] Experiment with try-catch-finally.
- [x] Use `throw` and `throws` in your own methods.
- [x] Create and use a custom exception.
- [x] Handle multiple exception types with multiple catch blocks.

---

**Excellent! Tomorrow you'll learn about wrapper classes and autoboxing.**