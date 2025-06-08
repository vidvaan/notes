# Day 16: Streams API – Basics

Today you'll learn about one of Java 8’s most powerful additions: the **Streams API**. Streams enable functional-style processing of collections with code that’s concise, readable, and often faster.

---

## 1. What Are Streams?

A **Stream** in Java represents a sequence of elements supporting sequential and parallel aggregate operations.
- NOT a data structure; does not store elements.
- Computes elements on-demand (lazily).
- Allows you to process data (filter, map, sort, etc.) in a pipeline.

**Key Properties:**
- Declarative: Focus on what, not how.
- Can be chained for complex processing.
- Can be parallelized for performance.

---

## 2. Creating Streams

### a. From Collections

```java
List<String> names = Arrays.asList("Alice", "Bob", "Carol");
Stream<String> stream = names.stream();
```

### b. From Arrays

```java
int[] numbers = {1, 2, 3, 4};
IntStream intStream = Arrays.stream(numbers);
```

### c. From Values

```java
Stream<String> stream = Stream.of("a", "b", "c");
```

### d. Infinite Streams

```java
Stream<Double> randoms = Stream.generate(Math::random).limit(5);
randoms.forEach(System.out::println);
```

---

## 3. Basic Stream Operations

Streams have two types of operations:

- **Intermediate:** Return a new stream (can be chained). Examples: `filter`, `map`, `sorted`
- **Terminal:** Produce a result or side-effect. Examples: `forEach`, `collect`, `count`, `reduce`

### a. Filter

Filter elements based on a condition.

```java
List<String> list = Arrays.asList("apple", "banana", "pear");
list.stream()
    .filter(s -> s.startsWith("b"))
    .forEach(System.out::println); // banana
```

### b. Map

Transform each element.

```java
List<String> list = Arrays.asList("a", "bb", "ccc");
list.stream()
    .map(String::length)
    .forEach(System.out::println); // 1 2 3
```

### c. forEach (Terminal Operation)

Perform an action for each element.

```java
list.stream().forEach(System.out::println);
```

### d. Collect

Gather the result into a collection.

```java
List<String> result = list.stream()
    .filter(s -> s.length() > 1)
    .collect(Collectors.toList());
System.out.println(result); // [bb, ccc]
```

### e. Count

Count the number of elements.

```java
long count = list.stream().count();
System.out.println(count); // 3
```

---

## 4. Example: Numbers Processing

```java
import java.util.*;
import java.util.stream.*;

public class StreamExample {
    public static void main(String[] args) {
        List<Integer> nums = Arrays.asList(2, 3, 4, 5, 6);

        // Filter even numbers, square them, collect to a list
        List<Integer> evensSquared = nums.stream()
            .filter(n -> n % 2 == 0)
            .map(n -> n * n)
            .collect(Collectors.toList());

        System.out.println(evensSquared); // [4, 36]
    }
}
```

---

## 5. Key Points

- Streams process data in a pipeline (source → intermediate ops → terminal op).
- Once a terminal operation is called, the stream is consumed.
- Streams do not modify the source data.
- Many stream methods use lambda expressions or method references.

---

## 🎯 Task Checklist

- [x] Create a stream from a collection and array.
- [x] Use `filter`, `map`, `forEach`, and `collect`.
- [x] Try counting, sorting, or finding max/min with streams.
- [x] Practice building small pipelines for data processing.

---

**Next: You’ll explore advanced stream operations, grouping, and parallel processing!**