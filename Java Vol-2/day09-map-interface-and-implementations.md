# Day 9: Map Interface and Implementations

Today's focus is on the `Map` interface in Java, how it works, its key implementations, and usage patterns for storing and processing key-value pairs.

---

## What is the Map Interface?

- A `Map` is a collection that stores **key-value pairs**.
- Each key is unique; values can be duplicated.
- Not a true child of the `Collection` interface but part of the Java Collections Framework.

---

## Main Implementations

### 1. HashMap

- Most commonly used `Map` implementation.
- **No guaranteed order** of keys.
- Fast for put/get/remove (O(1) average).
- Allows one null key and multiple null values.

```java
Map<String, Integer> map = new HashMap<>();
map.put("apple", 3);
map.put("banana", 2);
map.put("cherry", 5);
System.out.println(map); // {banana=2, apple=3, cherry=5} (order not guaranteed)
```

---

### 2. LinkedHashMap

- Maintains **insertion order** of entries.
- Slightly slower than HashMap but predictable iteration order.
- Also allows one null key and multiple null values.

```java
Map<String, Integer> map = new LinkedHashMap<>();
map.put("apple", 3);
map.put("banana", 2);
map.put("cherry", 5);
System.out.println(map); // {apple=3, banana=2, cherry=5}
```

---

### 3. TreeMap

- Stores entries **sorted by natural order of keys** or by a custom `Comparator`.
- No null keys (throws `NullPointerException`); values can be null.
- Slower (O(log n)) due to tree structure.

```java
Map<String, Integer> map = new TreeMap<>();
map.put("banana", 2);
map.put("apple", 3);
map.put("cherry", 5);
System.out.println(map); // {apple=3, banana=2, cherry=5}
```

---

## Map Methods and Key-Value Storage

- `put(K key, V value)`: Add or update key-value pairs.
- `get(Object key)`: Retrieve value by key.
- `remove(Object key)`: Remove key and its value.
- `containsKey(Object key)`, `containsValue(Object value)`: Check for presence.
- `size()`: Number of entries.
- `clear()`: Remove all entries.
- `isEmpty()`: Check if map is empty.
- `keySet()`: Returns a `Set` of all keys.
- `values()`: Returns a `Collection` of all values.
- `entrySet()`: Returns a `Set` of all key-value pairs as `Map.Entry` objects.

---

## Iterating Over Maps

### 1. Iterate by keySet

```java
for (String key : map.keySet()) {
    System.out.println("Key: " + key + ", Value: " + map.get(key));
}
```

### 2. Iterate by entrySet (most efficient)

```java
for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
}
```

### 3. Iterate by values

```java
for (Integer value : map.values()) {
    System.out.println("Value: " + value);
}
```

### 4. Java 8+ forEach

```java
map.forEach((k, v) -> System.out.println("Key: " + k + ", Value: " + v));
```

---

## Summary Table

| Implementation   | Order              | Null Keys | Performance      | Use Case                             |
|------------------|--------------------|-----------|------------------|--------------------------------------|
| HashMap          | None               | 1 allowed | Fastest (O(1))   | General key-value storage            |
| LinkedHashMap    | Insertion order    | 1 allowed | Fast (O(1))      | Order matters, LRU cache             |
| TreeMap          | Sorted by key      | Not allowed | Slower (O(log n)) | Sorted maps, range searches          |

---

**Practice:**
- Create a HashMap, LinkedHashMap, and TreeMap. Add, remove, and print entries.
- Iterate over a map using all four methods above.
- Try sorting custom objects as keys in a TreeMap using Comparator.

---