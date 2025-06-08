# Day 8: Set Interface and Implementations

Today you'll dive into the Set interface in Java, its main implementations, the importance of hashCode and equals, and ordering via Comparator and Comparable.

---

## Set Interface

- A Set is a collection that **does not allow duplicate elements**.
- Implementations do **not guarantee element order** (unless specified).
- Common uses: storing unique items, removing duplicates, set operations (union, intersection).

---

## Main Implementations

### 1. HashSet

- Backed by a hash table.
- **No guaranteed order** of elements.
- Fast for add, remove, contains (O(1) average).
- Elements must have correct `hashCode()` and `equals()` implementations for uniqueness.

```java
Set<String> set = new HashSet<>();
set.add("apple");
set.add("banana");
set.add("apple"); // Duplicate, will not be added
System.out.println(set); // [banana, apple] (order not guaranteed)
```

---

### 2. LinkedHashSet

- Extends HashSet.
- Maintains **insertion order**.
- Slightly slower than HashSet due to extra order-tracking.
- Useful when you need uniqueness and order.

```java
Set<String> set = new LinkedHashSet<>();
set.add("apple");
set.add("banana");
set.add("apple");
System.out.println(set); // [apple, banana]
```

---

### 3. TreeSet

- Stores elements in a **sorted (natural or custom) order**.
- Backed by a Red-Black tree.
- Slower (O(log n) for add, remove, contains) but always sorted.
- **Elements must be Comparable** or you must provide a **Comparator**.
- Does not allow null elements.

```java
Set<Integer> set = new TreeSet<>();
set.add(3);
set.add(1);
set.add(2);
System.out.println(set); // [1, 2, 3]
```

---

## Set Operations and Uniqueness

- **add(E e):** Adds the element if not already present.
- **remove(E e):** Removes the element if present.
- **contains(E e):** Checks if the element exists.
- **size():** Returns the number of unique elements.

**Set Algebra (using Java API):**
```java
Set<Integer> a = new HashSet<>(Arrays.asList(1, 2, 3));
Set<Integer> b = new HashSet<>(Arrays.asList(3, 4, 5));

// Union
Set<Integer> union = new HashSet<>(a);
union.addAll(b); // [1, 2, 3, 4, 5]

// Intersection
Set<Integer> intersection = new HashSet<>(a);
intersection.retainAll(b); // [3]

// Difference
Set<Integer> diff = new HashSet<>(a);
diff.removeAll(b); // [1, 2]
```

---

## hashCode() and equals()

- **hashCode():** Returns an integer hash; used by hash-based collections (HashSet, HashMap).
- **equals():** Checks logical equality between objects.

**Rules:**
- If two objects are equal (`equals()` returns true), they **must** have the same hashCode().
- If hashCode() is different, the objects are considered different in hash-based collections—even if equals() is true.

**Example:**

```java
class Person {
    String name;
    Person(String name) { this.name = name; }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Person)) return false;
        Person p = (Person) o;
        return Objects.equals(name, p.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name);
    }
}
```

**Without proper hashCode/equals, HashSet may allow duplicates!**

---

## Comparator and Comparable

### Comparable (Natural Ordering)

- Interface: `public interface Comparable<T> { int compareTo(T o); }`
- Used for **default sorting** (e.g., TreeSet, Collections.sort()).

```java
class Student implements Comparable<Student> {
    int id;
    Student(int id) { this.id = id; }
    @Override
    public int compareTo(Student other) {
        return this.id - other.id;
    }
}
```

### Comparator (Custom Ordering)

- Interface: `public interface Comparator<T> { int compare(T o1, T o2); }`
- Use when you want to define **multiple or custom sort orders**.

```java
class Student {
    String name;
    int age;
    // ... constructor, etc.
}

Comparator<Student> byAge = (s1, s2) -> s1.age - s2.age;
TreeSet<Student> students = new TreeSet<>(byAge);
```

- **TreeSet** can be created with a Comparator for custom order.

---

## Examples

**Custom ordering with TreeSet:**
```java
Set<String> set = new TreeSet<>(Comparator.reverseOrder());
set.add("apple");
set.add("banana");
set.add("cherry");
System.out.println(set); // [cherry, banana, apple]
```

**Comparable vs Comparator:**
- Use Comparable for “natural” order (e.g., alphabetical, numeric).
- Use Comparator for alternate orders (e.g., reverse, by a property).

---

## Summary Table

| Implementation   | Uniqueness | Order            | Performance | Usage                            |
|------------------|------------|------------------|-------------|----------------------------------|
| HashSet          | Yes        | No order         | Fastest     | Most common for unique elements  |
| LinkedHashSet    | Yes        | Insertion order  | Fast        | Need to preserve order           |
| TreeSet          | Yes        | Sorted order     | Slower      | Need sorted, unique elements     |

---

**Practice:**
- Create a HashSet, LinkedHashSet, and TreeSet. Add elements and observe order and uniqueness.
- Implement a class with proper hashCode and equals, and add to a HashSet.
- Try TreeSet with both Comparable and Comparator.

---