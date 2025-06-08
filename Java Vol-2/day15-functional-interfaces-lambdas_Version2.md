# Day 15: Functional Interfaces and Lambda Expressions

Today you'll master **functional interfaces** and **lambda expressions**—cornerstones of Java 8's functional programming model. You'll learn their syntax, use-cases, and how to leverage built-in and custom functional interfaces for cleaner, more expressive code.

---

## 1. What is a Functional Interface?

A **functional interface** is an interface with **exactly one abstract method**.  
- Can have default/static methods.
- Marked with `@FunctionalInterface` (recommended, but not required).
- Used as the target type for lambda expressions and method references.

**Example:**
```java
@FunctionalInterface
interface MyAction {
    void doSomething();
}
```

---

## 2. Lambda Expressions: Syntax & Use-cases

A lambda expression provides a clear and concise way to represent a single-method interface using an anonymous function.

**General Syntax:**
```java
(parameters) -> expression
(parameters) -> { statements }
```

**Examples:**
```java
Runnable r = () -> System.out.println("Running!");
Predicate<Integer> isEven = n -> n % 2 == 0;
Function<String, Integer> strLength = s -> s.length();
```

**Use-cases:**
- Event handling (e.g., GUI, threads)
- Collection operations (sorting, filtering, mapping)
- Passing behavior as parameters

---

## 3. Built-in Functional Interfaces (java.util.function)

Java provides many functional interfaces in `java.util.function` (and `java.util.concurrent` for `Callable`).

### 3.1 Predicate<T>
- **Purpose:** Test a condition; returns `true` or `false`.
- **Method:** `boolean test(T t)`
- **Example:**
  ```java
  Predicate<String> isShort = s -> s.length() < 5;
  System.out.println(isShort.test("Hi")); // true
  ```

### 3.2 Consumer<T>
- **Purpose:** Performs an action on an object; returns nothing.
- **Method:** `void accept(T t)`
- **Example:**
  ```java
  Consumer<String> printer = s -> System.out.println(s);
  printer.accept("Hello!"); // prints Hello!
  ```

### 3.3 Function<T, R>
- **Purpose:** Transforms an object of type T to type R.
- **Method:** `R apply(T t)`
- **Example:**
  ```java
  Function<String, Integer> toLength = s -> s.length();
  System.out.println(toLength.apply("Java")); // 4
  ```

### 3.4 Supplier<T>
- **Purpose:** Supplies a value; takes no arguments.
- **Method:** `T get()`
- **Example:**
  ```java
  Supplier<Double> random = () -> Math.random();
  System.out.println(random.get());
  ```

### 3.5 BiPredicate<T, U>
- **Purpose:** Tests a condition on two arguments.
- **Method:** `boolean test(T t, U u)`
- **Example:**
  ```java
  BiPredicate<String, Integer> isLongerThan = (s, n) -> s.length() > n;
  System.out.println(isLongerThan.test("hello", 3)); // true
  ```

### 3.6 BiConsumer<T, U>
- **Purpose:** Performs an action on two arguments.
- **Method:** `void accept(T t, U u)`
- **Example:**
  ```java
  BiConsumer<String, Integer> printNameAge = (name, age) -> 
      System.out.println(name + " is " + age + " years old.");
  printNameAge.accept("Alice", 21);
  ```

### 3.7 BiFunction<T, U, R>
- **Purpose:** Transforms two arguments into a result.
- **Method:** `R apply(T t, U u)`
- **Example:**
  ```java
  BiFunction<Integer, Integer, String> sumStr = (a, b) -> "Sum: " + (a + b);
  System.out.println(sumStr.apply(3, 4)); // Sum: 7
  ```

### 3.8 UnaryOperator<T>
- **Purpose:** A specialization of Function for the same type (T -> T).
- **Method:** `T apply(T t)`
- **Example:**
  ```java
  UnaryOperator<String> upper = s -> s.toUpperCase();
  System.out.println(upper.apply("java")); // JAVA
  ```

### 3.9 BinaryOperator<T>
- **Purpose:** A specialization of BiFunction for the same type (T, T -> T).
- **Method:** `T apply(T t1, T t2)`
- **Example:**
  ```java
  BinaryOperator<Integer> multiply = (a, b) -> a * b;
  System.out.println(multiply.apply(2, 3)); // 6
  ```

### 3.10 Callable<V> (java.util.concurrent)
- **Purpose:** Used for tasks that return a result and can throw an exception (e.g., in threads).
- **Method:** `V call() throws Exception`
- **Example:**
  ```java
  Callable<String> task = () -> "Done!";
  // Used with ExecutorService.submit(task)
  ```

### 3.11 Runnable (java.lang)
- **Purpose:** Represents a task with no return value, used for threads.
- **Method:** `void run()`
- **Example:**
  ```java
  Runnable runner = () -> System.out.println("Thread running!");
  new Thread(runner).start();
  ```

---

## 4. Custom Functional Interfaces

You can create your own functional interfaces for specific needs.

**Example:**
```java
@FunctionalInterface
interface MathOperation {
    int operate(int a, int b);
}

public class LambdaTest {
    public static void main(String[] args) {
        MathOperation add = (a, b) -> a + b;
        MathOperation mul = (a, b) -> a * b;
        System.out.println(add.operate(2, 3)); // 5
        System.out.println(mul.operate(2, 3)); // 6
    }
}
```

---

## 5. Summary Table

| Interface            | Method Signature                           | Usage Example     |
|----------------------|--------------------------------------------|-------------------|
| Predicate<T>         | boolean test(T)                            | Filtering         |
| Consumer<T>          | void accept(T)                             | ForEach/Print     |
| Function<T, R>       | R apply(T)                                 | Mapping/Transform |
| Supplier<T>          | T get()                                    | Factories         |
| BiPredicate<T, U>    | boolean test(T, U)                         | Two-arg filter    |
| BiConsumer<T, U>     | void accept(T, U)                          | Two-arg action    |
| BiFunction<T,U,R>    | R apply(T, U)                              | Two-arg transform |
| UnaryOperator<T>     | T apply(T)                                 | Modify T to T     |
| BinaryOperator<T>    | T apply(T, T)                              | Combine T, T      |
| Callable<V>          | V call() throws Exception                  | Tasks with result |
| Runnable             | void run()                                 | Tasks/threads     |

---

## 🎯 Task Checklist

- [x] Write lambdas for various built-in functional interfaces.
- [x] Create and use a custom functional interface.
- [x] Use lambdas in collections (forEach, filter, map).
- [x] Try combining interfaces for more complex logic.

---

**Next: You'll dive into the Streams API for powerful data processing!**