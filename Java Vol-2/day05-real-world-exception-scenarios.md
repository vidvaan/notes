# Day 5: Real-World Exception Scenarios

Today you'll learn how to apply exception handling to common real-world programming scenarios and how to properly log exceptions.

---

## Exception Handling in File I/O

File operations (reading, writing, closing) often throw checked exceptions, such as `IOException` or `FileNotFoundException`. Proper handling ensures your program doesn’t crash and resources are safely managed.

**Example: Reading a file with try-with-resources**
```java
import java.io.*;

public class FileReadExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (FileNotFoundException e) {
            System.err.println("File not found: " + e.getMessage());
        } catch (IOException e) {
            System.err.println("I/O error: " + e.getMessage());
        }
    }
}
```
- Use try-with-resources to automatically close files.
- Catch both `FileNotFoundException` and `IOException` for robust handling.

---

## Exception Handling in Collections and Streams

Exceptions in collections typically involve invalid indices, nulls, or unsupported operations. Streams (Java 8+) may result in exceptions inside lambda expressions.

**Example: Handling exceptions in collections**
```java
import java.util.*;

public class CollectionExample {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("A", "B", "C");
        try {
            System.out.println(list.get(5)); // Index out of bounds
        } catch (IndexOutOfBoundsException e) {
            System.err.println("Invalid index: " + e.getMessage());
        }
    }
}
```

**Example: Exception handling in streams**
```java
import java.util.*;
import java.util.stream.*;

public class StreamExample {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("10", "20", "abc", "30");
        list.stream().forEach(s -> {
            try {
                int num = Integer.parseInt(s);
                System.out.println(num);
            } catch (NumberFormatException e) {
                System.err.println("Invalid number: " + s);
            }
        });
    }
}
```

---

## Logging Exceptions

Logging exceptions is better than just printing stack traces. Use logging frameworks (e.g., `java.util.logging`, Log4j, SLF4J) for production code.

**Example: Using java.util.logging**
```java
import java.util.logging.*;
import java.io.*;

public class LoggingExample {
    private static final Logger logger = Logger.getLogger(LoggingExample.class.getName());
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("missing.txt"))) {
            br.readLine();
        } catch (IOException e) {
            logger.log(Level.SEVERE, "File operation failed", e);
        }
    }
}
```

**Best Practices:**
- Log the exception message and stack trace.
- Use appropriate logging levels (`SEVERE`, `WARNING`, `INFO`, etc.).
- Never swallow exceptions silently.

---

**Practice:**
- Write a program that reads from a file and logs any exceptions.
- Experiment with exception handling in lists and streams.
- Use a logger instead of `System.out` or `System.err`.

---