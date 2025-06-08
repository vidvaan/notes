# Day 21: Introduction to Collections

Welcome to Day 21! Today you'll learn about Java's **Collections Framework**, which provides powerful tools to store, manage, and manipulate groups of objects. You'll focus on the core interfaces—**List**, **Set**, **Map**—and their common implementations: **ArrayList**, **HashSet**, and **HashMap**.

---

## 1. What are Collections?

- **Collections** are objects that group multiple elements into a single unit (like a dynamic array or a set).
- Java Collections Framework provides interfaces and classes to efficiently store, retrieve, and process data.

---

## 2. Core Collection Interfaces

| Interface | Description                               | Allows Duplicates? | Maintains Order? |
|-----------|-------------------------------------------|--------------------|------------------|
| List      | Ordered collection (like a list/array)    | Yes                | Yes              |
| Set       | Unordered collection of unique elements   | No                 | No (usually)     |
| Map       | Key-value pairs (like a dictionary)       | Keys: No           | No (usually)     |

---

## 3. ArrayList (List Implementation)

- **ArrayList** is a dynamic array that grows as needed.
- Maintains insertion order, allows duplicates.

**Example:**
```java
import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Apple"); // Duplicates allowed
        System.out.println(fruits); // [Apple, Banana, Apple]
        System.out.println("First fruit: " + fruits.get(0)); // Apple
    }
}
```

---

## 4. HashSet (Set Implementation)

- **HashSet** stores unique elements in no particular order.
- Fast for add, remove, and check operations.

**Example:**
```java
import java.util.HashSet;

public class HashSetDemo {
    public static void main(String[] args) {
        HashSet<Integer> numbers = new HashSet<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(10); // Duplicate, won't be added
        System.out.println(numbers); // e.g., [20, 10]
        System.out.println("Has 20? " + numbers.contains(20)); // true
    }
}
```

---

## 5. HashMap (Map Implementation)

- **HashMap** stores key-value pairs.
- Keys must be unique, values can be duplicated.
- No guaranteed order of elements.

**Example:**
```java
import java.util.HashMap;

public class HashMapDemo {
    public static void main(String[] args) {
        HashMap<String, Integer> scores = new HashMap<>();
        scores.put("Alice", 85);
        scores.put("Bob", 90);
        scores.put("Alice", 95); // Overwrites previous value for "Alice"
        System.out.println(scores); // {Bob=90, Alice=95}
        System.out.println("Bob's score: " + scores.get("Bob")); // 90
    }
}
```

---

## 6. When to Use Which?

- **ArrayList**: When you need an ordered, index-based collection (like a list of items).
- **HashSet**: When you need to store unique items with no duplicates.
- **HashMap**: When you need to associate keys with values (like a dictionary).

---

## 7. Iterating Collections

**List Example:**
```java
for (String fruit : fruits) {
    System.out.println(fruit);
}
```

**Set Example:**
```java
for (Integer num : numbers) {
    System.out.println(num);
}
```

**Map Example:**
```java
for (String key : scores.keySet()) {
    System.out.println(key + ": " + scores.get(key));
}
```

---

## 🎯 Task Checklist

- [x] Create and use an `ArrayList` for a list of items.
- [x] Use a `HashSet` to store unique values.
- [x] Use a `HashMap` to associate keys and values.
- [x] Iterate through each collection using a loop.

---

**Awesome! Next, you'll learn about File Input/Output in Java.**