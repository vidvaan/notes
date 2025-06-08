# Day 2: Advanced Exception Handling

## Multiple Catch Blocks

- You can have several `catch` blocks to handle different types of exceptions separately.
- The order matters: catch more specific exceptions first, then general ones.

```java
try {
    int[] arr = new int[3];
    System.out.println(arr[5]); // May throw ArrayIndexOutOfBoundsException
    int result = 10 / 0;        // May throw ArithmeticException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index out of range: " + e.getMessage());
} catch (ArithmeticException e) {
    System.out.println("Arithmetic error: " + e.getMessage());
} catch (Exception e) {
    System.out.println("General error: " + e.getMessage());
}
```

---

## Multi-catch (`catch (A | B e)`)

- Java allows you to catch multiple exception types in a single `catch` block using the pipe symbol `|`.

```java
try {
    // code that may throw either IOException or SQLException
} catch (IOException | SQLException e) {
    System.out.println("IO or SQL error: " + e.getMessage());
}
```

---

## Nested try-catch

- A `try-catch` block can exist inside another `try` or `catch` block.
- Useful when some exceptions need to be handled at different levels.

```java
try {
    try {
        int num = Integer.parseInt("abc");
    } catch (NumberFormatException e) {
        System.out.println("Inner: Invalid number format.");
    }
    int[] arr = new int[2];
    System.out.println(arr[3]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Outer: Array index error.");
}
```

---

## Exception Propagation

- When an exception is not caught in the current method, it is propagated to the caller.
- You can use the `throws` keyword to declare that your method might throw certain exceptions.

```java
void readFile() throws IOException {
    // code that may throw IOException
}

void process() {
    try {
        readFile();
    } catch (IOException e) {
        System.out.println("Handled in process(): " + e.getMessage());
    }
}
```

---

**Practice:**
- Write a program that demonstrates multiple catch blocks, multi-catch, nested try-catch, and exception propagation.
- Try deliberately causing different exceptions and observing which catch block handles them.

---