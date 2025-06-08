# Day 7: List Interface and Implementations

Today you'll explore the `List` interface in Java, its main implementations, and how to use and choose between them.

---

## ArrayList vs. LinkedList vs. Vector vs. Stack

| Class        | Backing Structure | Thread-Safe | Access Time | Insert/Delete | Legacy | Notes                        |
|--------------|------------------|-------------|-------------|--------------|--------|------------------------------|
| ArrayList    | Dynamic array     | No          | Fast (O(1)) | Slow (O(n))  | No     | Most used, not synchronized  |
| LinkedList   | Doubly linked     | No          | Slow (O(n)) | Fast at ends | No     | Good for frequent inserts    |
| Vector       | Dynamic array     | Yes         | Fast (O(1)) | Slow (O(n))  | Yes    | Synchronized, legacy         |
| Stack        | Extends Vector    | Yes         | Fast (O(1)) | -            | Yes    | LIFO, use Deque for new code |

---

## List Methods and Performance

Common `List` methods:
- `add(E e)`, `add(int index, E e)`
- `get(int index)`
- `set(int index, E e)`
- `remove(int index)`, `remove(Object o)`
- `size()`
- `contains(Object o)`
- `indexOf(Object o)`, `lastIndexOf(Object o)`
- `clear()`
- `isEmpty()`
- `sort(Comparator<? super E> c)`

**Performance:**
- **ArrayList/Vector**: Fast random access (`get/set`), slow middle inserts/removes.
- **LinkedList**: Fast inserts/removes at ends, slow random access.
- **Vector/Stack**: Like ArrayList, but synchronized (slower, thread-safe).

---

## Iteration, Sorting, Searching

### Iteration

```java
List<String> list = Arrays.asList("A", "B", "C");

// For loop
for(int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}

// Enhanced for
for(String s : list) {
    System.out.println(s);
}

// Iterator
Iterator<String> it = list.iterator();
while(it.hasNext()) {
    System.out.println(it.next());
}

// Java 8+
list.forEach(System.out::println);
```

---

### Sorting

```java
List<Integer> nums = Arrays.asList(4, 2, 7, 1);
Collections.sort(nums); // Ascending
nums.sort(Collections.reverseOrder()); // Descending
```

---

### Searching

```java
List<String> list = Arrays.asList("A", "B", "C", "B");
int idx = list.indexOf("B");        // 1
int lastIdx = list.lastIndexOf("B"); // 3
boolean found = list.contains("C");  // true
```

---

## Summary

- **Use ArrayList** for most needs (fast access, unsynchronized).
- **Use LinkedList** for frequent insertions/removals at ends.
- **Use Vector/Stack** only for legacy code; prefer `ArrayDeque` for stack/queue in new code.
- Know your methods for manipulating, sorting, and searching lists.

---

**Practice:**
- Create an `ArrayList` and `LinkedList`, add/remove elements, and compare performance.
- Sort a list of strings and search for elements.
- Try iterating using all four methods above.

---