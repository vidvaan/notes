# Day 3: Custom Exceptions

Learn how to create, use, and apply best practices for user-defined exceptions in Java.

---

## Creating User-Defined Exceptions

You can create your own exception classes by extending the `Exception` class (for checked exceptions) or the `RuntimeException` class (for unchecked exceptions).

**Example: Checked Exception**
```java
public class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}
```

**Example: Unchecked Exception**
```java
public class MyUncheckedException extends RuntimeException {
    public MyUncheckedException(String message) {
        super(message);
    }
}
```

---

## Using `throw` and `throws`

- **`throw`:** Used to explicitly throw an exception in code.
- **`throws`:** Used in method signatures to declare that a method may throw certain exceptions.

**Example: Using throw and throws**
```java
public void setAge(int age) throws InvalidAgeException {
    if (age < 0) {
        throw new InvalidAgeException("Age cannot be negative.");
    }
    // ... set age
}
```

```java
try {
    setAge(-5);
} catch (InvalidAgeException e) {
    System.out.println("Caught Exception: " + e.getMessage());
}
```

---

## Best Practices for Custom Exceptions

- **Name Meaningfully:** Name your exception to clearly indicate the problem (e.g., `InvalidAgeException`).
- **Extend Correct Base Class:** Extend `Exception` for checked, `RuntimeException` for unchecked.
- **Include Constructors:** Provide constructors to accept custom messages and (optionally) cause.
- **Document Usage:** Clearly document when and why your exception should be thrown.
- **Don’t Overuse:** Use custom exceptions only when standard exceptions are insufficient.
- **Keep Exception Classes Lightweight:** Avoid adding unnecessary fields or logic.

**Example: Full Custom Exception Class**
```java
public class InvalidAgeException extends Exception {
    public InvalidAgeException() {
        super();
    }
    public InvalidAgeException(String message) {
        super(message);
    }
    public InvalidAgeException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

---

**Practice:**
- Create a custom exception for a business rule (e.g., `InsufficientBalanceException`).
- Use `throw` and `throws` in your code to demonstrate handling this exception.

---