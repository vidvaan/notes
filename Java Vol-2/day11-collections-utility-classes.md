# Day 11: Collections Utility Classes

Today you'll learn about Java's utility classes for collections, focusing on powerful static methods for manipulating and protecting data structures.

---

## Collections and Arrays Utility Methods

Java provides two main utility classes:

- **`java.util.Collections`**: Static methods for common operations on collections (lists, sets, maps, etc.).
- **`java.util.Arrays`**: Static methods for array operations.

---

## Sorting, Searching, Shuffling

### Sorting

- **Collections.sort**: Sorts a list using natural order or a custom comparator.
    ```java
    List<Integer> list = Arrays.asList(3, 2, 5, 1);
    Collections.sort(list); // [1, 2, 3, 5]

    // Custom comparator
    Collections.sort(list, Collections.reverseOrder()); // [5, 3, 2, 1]
    ```

- **Arrays.sort**: Sorts arrays.
    ```java
    int[] arr = {3, 2, 5, 1};
    Arrays.sort(arr); // [1, 2, 3, 5]
    ```

### Searching

- **Collections.binarySearch**: Searches a *sorted* list for an element.
    ```java
    List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
    Collections.sort(names);
    int index = Collections.binarySearch(names, "Bob"); // index = 1
    ```

- **Arrays.binarySearch**: Searches a *sorted* array.
    ```java
    int[] arr = {1, 2, 3, 5};
    int idx = Arrays.binarySearch(arr, 3); // idx = 2
    ```

### Shuffling

- **Collections.shuffle**: Randomly permutes the elements in a list.
    ```java
    List<Integer> nums = Arrays.asList(1, 2, 3, 4, 5);
    Collections.shuffle(nums);
    ```

---

## Synchronized Collections

- By default, Java collections are **not thread-safe**.
- Use the `Collections.synchronizedXxx()` methods to get synchronized (thread-safe) versions.

**Examples:**
```java
List<String> syncList = Collections.synchronizedList(new ArrayList<>());
Set<Integer> syncSet = Collections.synchronizedSet(new HashSet<>());
Map<String, String> syncMap = Collections.synchronizedMap(new HashMap<>());
```

- Access must still be synchronized manually when iterating:
    ```java
    synchronized(syncList) {
        for (String s : syncList) {
            // safely iterate
        }
    }
    ```

---

## Immutable Collections

- Immutable collections **cannot be modified** after creation.
- Java 9+ provides convenient factory methods:

**Examples:**
```java
List<String> immutableList = List.of("A", "B", "C");
Set<Integer> immutableSet = Set.of(1, 2, 3);
Map<String, Integer> immutableMap = Map.of("one", 1, "two", 2);
```
- Any attempt to modify (add, remove, set, etc.) will throw `UnsupportedOperationException`.

- Pre-Java 9, use:
    ```java
    List<String> unmodifiable = Collections.unmodifiableList(new ArrayList<>(list));
    ```

---

## Summary Table

| Operation      | Utility Class      | Method Example                      |
|----------------|-------------------|-------------------------------------|
| Sort List      | Collections       | Collections.sort(list)              |
| Sort Array     | Arrays            | Arrays.sort(array)                  |
| Search List    | Collections       | Collections.binarySearch(list, el)  |
| Search Array   | Arrays            | Arrays.binarySearch(array, el)      |
| Shuffle List   | Collections       | Collections.shuffle(list)           |
| Synchronized   | Collections       | Collections.synchronizedList(list)  |
| Immutable      | List/Set/Map (9+) | List.of(), Set.of(), Map.of()       |

---

**Practice:**
- Sort and shuffle a list using `Collections`.
- Search for elements using `binarySearch`.
- Create synchronized and immutable collections, and try modifying them to observe exceptions.

---