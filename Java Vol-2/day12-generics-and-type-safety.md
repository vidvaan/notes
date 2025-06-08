# Day 12: Generics and Type Safety

Today you'll learn about Java Generics—why they exist, how to use them, and how to write safer, reusable code.

---

## Why Generics?

- **Type Safety:** Catch errors at compile time, avoid `ClassCastException`.
- **Code Reuse:** Write classes and methods that work with any type.
- **Eliminate Casts:** No need for explicit casting when retrieving elements.

**Example:**

```java
List<String> names = new ArrayList<>();
names.add("Alice");
// names.add(123); // Compile-time error!
String name = names.get(0); // No cast needed
```

---

## Creating Generic Classes and Methods

### Generic Class

```java
// T is the type parameter
public class Box<T> {
    private T item;
    public void set(T item) { this.item = item; }
    public T get() { return item; }
}

// Usage
Box<Integer> intBox = new Box<>();
intBox.set(100);
Integer value = intBox.get();
```

### Generic Method

```java
public class Util {
    public static <T> void printArray(T[] array) {
        for (T item : array) {
            System.out.println(item);
        }
    }
}

// Usage
String[] arr = {"A", "B", "C"};
Util.printArray(arr);
```

---

## Bounded Types

- **Upper Bound (`extends`):** Restrict type to a subclass/specific interface.
    ```java
    public <T extends Number> void sum(T a, T b) {
        // Can use Number methods
    }
    ```

- **Lower Bound (`super`):** Rarely used, allows type and its supertypes.
    ```java
    public <T super Integer> void addToList(List<T> list) { ... } // Not allowed with generic methods—see wildcards below.
    ```

---

## Wildcards: `?`, `extends`, `super`

Wildcards allow flexibility when specifying generic types.

### Unbounded Wildcard: `?`

- Matches any type.
    ```java
    List<?> list = new ArrayList<String>();
    list = new ArrayList<Integer>();
    ```

### Upper Bounded Wildcard: `? extends T`

- Accepts `T` or any subclass of `T`.
    ```java
    List<? extends Number> nums = new ArrayList<Integer>();
    ```

### Lower Bounded Wildcard: `? super T`

- Accepts `T` or any superclass of `T`.
    ```java
    List<? super Integer> nums = new ArrayList<Number>();
    nums = new ArrayList<Object>();
    ```

### Example: Wildcards in Methods

```java
public static void printNumbers(List<? extends Number> list) {
    for (Number n : list) {
        System.out.println(n);
    }
}

public static void addIntegers(List<? super Integer> list) {
    list.add(1); // Allowed
    // Integer value can be safely added
}
```

---

## Summary Table

| Syntax                      | Meaning                                 | Example Usage                     |
|-----------------------------|-----------------------------------------|-----------------------------------|
| `List<T>`                   | Specific type                           | `List<String>`                    |
| `List<?>`                   | Any type                                | `List<?>`                         |
| `List<? extends Number>`    | Number or subclass                      | `List<Integer>`, `List<Double>`   |
| `List<? super Integer>`     | Integer or superclass                   | `List<Number>`, `List<Object>`    |

---

**Practice:**
- Write a generic `Pair<T, U>` class.
- Write a method to sum elements of a `List<? extends Number>`.
- Experiment with wildcards and bounded types in collections.

---