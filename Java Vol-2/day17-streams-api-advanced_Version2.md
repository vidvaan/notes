# Day 17: Streams API – Advanced

Today you'll build on your Streams knowledge by exploring **intermediate and terminal operations**, advanced **Collectors** (grouping/partitioning), and **parallel streams**. Each concept is explained with a simple description and example.

---

## 1. Intermediate Operations

These return a stream and can be chained; they don’t trigger processing by themselves.

### a. filter
- **Description:** Keeps elements that match a condition.
- **Example:**
  ```java
  Stream.of(1, 2, 3).filter(n -> n > 1).forEach(System.out::println); // 2, 3
  ```

### b. map
- **Description:** Transforms each element.
- **Example:**
  ```java
  Stream.of("a", "bb").map(String::toUpperCase).forEach(System.out::println); // A, BB
  ```

### c. flatMap
- **Description:** Flattens nested streams into a single stream.
- **Example:**
  ```java
  List<List<String>> data = Arrays.asList(Arrays.asList("A", "B"), Arrays.asList("C"));
  data.stream().flatMap(List::stream).forEach(System.out::println); // A B C
  ```

### d. distinct
- **Description:** Removes duplicates.
- **Example:**
  ```java
  Stream.of(1, 2, 2, 3).distinct().forEach(System.out::println); // 1, 2, 3
  ```

### e. sorted
- **Description:** Sorts elements (natural or with a Comparator).
- **Example:**
  ```java
  Stream.of(3, 1, 2).sorted().forEach(System.out::println); // 1, 2, 3
  ```

### f. limit / skip
- **Description:** limit returns only the first n elements; skip skips the first n.
- **Example:**
  ```java
  Stream.of(1, 2, 3, 4).limit(2).forEach(System.out::println); // 1, 2
  Stream.of(1, 2, 3, 4).skip(2).forEach(System.out::println);  // 3, 4
  ```

### g. peek
- **Description:** Performs an action on each element as it passes through, mainly for debugging.
- **Example:**
  ```java
  Stream.of(1, 2).peek(System.out::println).map(n -> n * 10).forEach(System.out::println);
  ```

---

## 2. Terminal Operations

These trigger stream processing and return a non-stream result.

### a. forEach
- **Description:** Performs an action for each element.
- **Example:**
  ```java
  Stream.of("A", "B").forEach(System.out::println); // A B
  ```

### b. collect
- **Description:** Gathers results into a collection or summary.
- **Example:**
  ```java
  List<Integer> list = Stream.of(1, 2).collect(Collectors.toList());
  ```

### c. reduce
- **Description:** Combines elements into a single value.
- **Example:**
  ```java
  int sum = Stream.of(1, 2, 3).reduce(0, Integer::sum); // 6
  ```

### d. count
- **Description:** Counts elements in the stream.
- **Example:**
  ```java
  long count = Stream.of(1, 2, 3).count(); // 3
  ```

### e. min / max
- **Description:** Finds the minimum/maximum element.
- **Example:**
  ```java
  int min = Stream.of(3, 1, 2).min(Integer::compare).get(); // 1
  ```

### f. anyMatch / allMatch / noneMatch
- **Description:** Checks if any/all/none of the elements match a condition.
- **Example:**
  ```java
  boolean hasEven = Stream.of(1, 2, 3).anyMatch(n -> n % 2 == 0); // true
  ```

### g. findFirst / findAny
- **Description:** Gets the first/any element from the stream.
- **Example:**
  ```java
  Optional<Integer> first = Stream.of(5, 6, 7).findFirst(); // 5
  ```

---

## 3. Collectors: Grouping and Partitioning

### a. groupingBy
- **Description:** Groups elements by a classifier function.
- **Example:**
  ```java
  Map<Integer, List<String>> byLength = Stream.of("a", "bb", "cc")
      .collect(Collectors.groupingBy(String::length));
  // {1=[a], 2=[bb, cc]}
  ```

### b. partitioningBy
- **Description:** Divides elements into two groups (true/false) based on a predicate.
- **Example:**
  ```java
  Map<Boolean, List<Integer>> evens = Stream.of(1, 2, 3, 4)
      .collect(Collectors.partitioningBy(n -> n % 2 == 0));
  // {false=[1, 3], true=[2, 4]}
  ```

### c. joining
- **Description:** Concatenates elements into a single string.
- **Example:**
  ```java
  String result = Stream.of("a", "b", "c").collect(Collectors.joining(","));
  // "a,b,c"
  ```

### d. summarizingInt / summarizingDouble
- **Description:** Calculates statistics (count, sum, min, avg, max) for numeric properties.
- **Example:**
  ```java
  IntSummaryStatistics stats = Stream.of(1,2,3).collect(Collectors.summarizingInt(n -> n));
  // stats.getAverage(), stats.getMax(), etc.
  ```

---

## 4. Parallel Streams

- **Description:** Enable parallel processing for faster operations on large datasets.
- **Usage:** Use `.parallelStream()` or call `.parallel()` on a stream.

**Example:**
```java
List<Integer> nums = Arrays.asList(1,2,3,4,5,6,7,8,9,10);
long count = nums.parallelStream().filter(n -> n % 2 == 0).count();
System.out.println(count); // 5
```
- **Caution:** Parallel streams are easy to use but can be less efficient for small datasets or when side-effects are present.

---

## 🎯 Task Checklist

- [x] Practice with intermediate and terminal operations.
- [x] Use groupingBy and partitioningBy collectors.
- [x] Try parallel streams for a large dataset.
- [x] Combine multiple operations in a stream pipeline.

---

**Next: Dive into the modern Date and Time API!**