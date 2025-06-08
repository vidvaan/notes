# Day 4: Exception Handling Best Practices

Today you'll learn professional practices for robust, safe, and maintainable exception handling in Java.

---

## Catching vs. Rethrowing

**Catching**: Handle the exception where it occurs, often logging or taking corrective action.

**Rethrowing**: If you cannot handle the exception meaningfully, rethrow it so that it can be handled at a higher level.

```java
try {
    // code that may throw an exception
} catch (IOException e) {
    // log and rethrow
    System.err.println("Logging: " + e.getMessage());
    throw e; // rethrow for higher-level handling
}
```

- **Best Practice**: Only catch exceptions you can handle properly. Otherwise, let them propagate.

---

## Resource Management

Resources like files, database connections, or sockets must be closed after use to avoid resource leaks.

**Old style (with finally):**

```java
FileInputStream fis = null;
try {
    fis = new FileInputStream("data.txt");
    // use fis
} catch (IOException e) {
    System.out.println("IO error: " + e.getMessage());
} finally {
    if (fis != null) {
        try {
            fis.close();
        } catch (IOException e) {
            System.out.println("Failed to close the file.");
        }
    }
}
```

---

## Using finally

- The `finally` block always executes, regardless of whether an exception is thrown or caught.
- Use it for cleanup (closing files, releasing resources).

```java
try {
    // risky code
} catch (Exception e) {
    // handle exception
} finally {
    // always runs
    System.out.println("Cleanup here");
}
```

---

## Try-with-Resources

Introduced in Java 7, this statement automatically closes resources that implement `AutoCloseable`.

```java
try (FileInputStream fis = new FileInputStream("data.txt")) {
    // use fis
} catch (IOException e) {
    System.out.println("IO error: " + e.getMessage());
}
// fis is automatically closed
```

- **Best Practice**: Prefer try-with-resources for automatic and safe resource management.

---

## Summary of Best Practices

- Catch only those exceptions you can meaningfully handle.
- Clean up resources using finally or try-with-resources.
- Prefer try-with-resources for all AutoCloseable resources.
- Rethrow exceptions if you cannot handle them at the current level.
- Always log exceptions or provide enough context when rethrowing.

---

**Practice:**
- Write a program that reads from a file and demonstrates both finally and try-with-resources.
- Experiment with catching and rethrowing exceptions.

---