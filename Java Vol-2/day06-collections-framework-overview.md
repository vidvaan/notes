# Day 6: Collections Framework Overview

Today you'll get an overview of the Java Collections Framework, its core interfaces, and common implementations.

---

## What is the Collections Framework?

The **Collections Framework** is a unified architecture in Java for storing, retrieving, and manipulating groups of objects. It provides:

- Common interfaces for different types of collections
- Implementations (classes) for reusable data structures
- Algorithms to operate on collections (e.g., sorting, searching)
- Utilities for thread safety, synchronization, and more

---

## Core Interfaces

### 1. `Collection<E>`
- The root interface for most collection types (except maps).
- Extended by List, Set, and Queue.

### 2. `List<E>`
- Ordered collection (elements can be accessed by index).
- Allows duplicates.
- Examples: `ArrayList`, `LinkedList`, `Vector`

### 3. `Set<E>`
- Unordered collection of unique elements (no duplicates).
- Examples: `HashSet`, `LinkedHashSet`, `TreeSet`

### 4. `Queue<E>`
- Designed for holding elements prior to processing (FIFO).
- Examples: `LinkedList` (as queue), `PriorityQueue`, `ArrayDeque`

### 5. `Map<K, V>`
- Object that maps keys to values (no duplicate keys).
- Not a true child of `Collection` but part of the framework.
- Examples: `HashMap`, `TreeMap`, `LinkedHashMap`, `Hashtable`

---

## Common Implementations Overview

| Interface   | Implementation        | Features/Use Cases                              |
|-------------|----------------------|-------------------------------------------------|
| List        | `ArrayList`          | Fast random access, resizable array             |
|             | `LinkedList`         | Fast insertion/removal, can act as queue/deque  |
|             | `Vector`             | Synchronized version of ArrayList (legacy)      |
| Set         | `HashSet`            | Fast, unordered, unique elements                |
|             | `LinkedHashSet`      | Maintains insertion order                       |
|             | `TreeSet`            | Sorted, unique elements                         |
| Queue       | `PriorityQueue`      | Elements ordered by priority                    |
|             | `ArrayDeque`         | Fast, resizable double-ended queue              |
| Map         | `HashMap`            | Fast, unordered key-value pairs                 |
|             | `TreeMap`            | Sorted keys                                     |
|             | `LinkedHashMap`      | Maintains insertion order                       |
|             | `Hashtable`          | Synchronized, legacy                            |

---

**Practice:**
- Create an `ArrayList` of strings, add elements, and iterate.
- Use a `HashSet` to store unique integers.
- Create a `HashMap` mapping names to ages and print all entries.
- Try using a `PriorityQueue` for integers.

---