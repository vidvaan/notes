# Day 25: Lambda Expressions & Functional Interfaces (Java 8+)

Welcome to Day 25! Today you'll learn about **lambda expressions** and **functional interfaces**—powerful features introduced in Java 8 that make your code cleaner, more concise, and enable functional programming styles.

---

## 1. What is a Lambda Expression?

- A **lambda expression** is a concise way to represent an **anonymous method** (a function without a name).
- Syntax:  
  ```
  (parameters) -> expression
  ```
- Lambdas are most useful when working with interfaces that have a single abstract method (**functional interfaces**).

---

## 2. What is a Functional Interface?

- An interface with **exactly one abstract method**.
- Can have default and static methods.
- Marked with `@FunctionalInterface` annotation (optional but recommended).

**Example:**
```java
@FunctionalInterface
interface MyFunc {
    void show();
}
```

---

## 3. Basic Lambda Syntax

**Standard syntax:**
```java
(parameter1, parameter2) -> { /* body */ }
```

**Examples:**
```java
// No parameters
() -> System.out.println("Hello, Lambda!");

// One parameter (parentheses optional)
x -> x * x;

// Multiple parameters
(a, b) -> a + b;

// With a block
(x, y) -> {
    int sum = x + y;
    return sum;
};
```

---

## 4. Using Lambdas with Functional Interfaces

**Example:**
```java
@FunctionalInterface
interface Greet {
    void message(String name);
}

public class LambdaDemo {
    public static void main(String[] args) {
        Greet g = (name) -> System.out.println("Hello, " + name + "!");
        g.message("Vidvaan"); // Output: Hello, Vidvaan!
    }
}
```

---

## 5. Common Built-in Functional Interfaces

Java provides many commonly used functional interfaces in `java.util.function` package:

| Interface      | Method Signature                        | Example Use           |
|----------------|----------------------------------------|-----------------------|
| Predicate<T>   | boolean test(T t)                      | Filtering             |
| Consumer<T>    | void accept(T t)                       | Action (forEach)      |
| Supplier<T>    | T get()                                | Factory/generator     |
| Function<T,R>  | R apply(T t)                           | Transformation        |

---

**Examples:**

```java
import java.util.function.*;

public class BuiltInLambdaDemo {
    public static void main(String[] args) {
        // Predicate: test if number is even
        Predicate<Integer> isEven = n -> n % 2 == 0;
        System.out.println(isEven.test(4)); // true

        // Consumer: print a value
        Consumer<String> printer = s -> System.out.println(s);
        printer.accept("Lambda rocks!");

        // Supplier: provide a value
        Supplier<Double> randomSupplier = () -> Math.random();
        System.out.println(randomSupplier.get());

        // Function: convert string to length
        Function<String, Integer> strLength = s -> s.length();
        System.out.println(strLength.apply("hello")); // 5
    }
}
```

---

## 6. Common Use Cases

- **Iterating collections:**
    ```java
    import java.util.*;
    public class ForEachDemo {
        public static void main(String[] args) {
            List<String> names = Arrays.asList("Alice", "Bob", "Carol");
            names.forEach(name -> System.out.println(name));
        }
    }
    ```

- **Sorting with Comparator:**
    ```java
    List<Integer> nums = Arrays.asList(5, 1, 3, 2);
    nums.sort((a, b) -> a - b);
    System.out.println(nums); // [1, 2, 3, 5]
    ```

- **Filtering with streams:**
    ```java
    List<Integer> nums = Arrays.asList(1, 2, 3, 4, 5, 6);
    nums.stream().filter(n -> n % 2 == 0).forEach(System.out::println); // 2 4 6
    ```

---

## 7. Lambda vs Anonymous Inner Class

**Before Java 8:**
```java
Runnable r = new Runnable() {
    public void run() {
        System.out.println("Old way");
    }
};
```
**With Lambda:**
```java
Runnable r = () -> System.out.println("New way!");
```

---

## 🎯 Task Checklist

- [x] Write your own functional interface and use a lambda expression.
- [x] Use built-in functional interfaces: `Predicate`, `Consumer`, `Supplier`, `Function`.
- [x] Iterate a collection with a lambda.
- [x] Use a lambda to sort or filter a list.

---

**Nice! Tomorrow you'll explore more useful Java APIs.**