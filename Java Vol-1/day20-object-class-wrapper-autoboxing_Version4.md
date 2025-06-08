# Day 20: Object Class, Wrapper Classes & Autoboxing

Welcome to Day 20! Today, you'll learn about the **Object class** (the root of all Java classes), as well as **wrapper classes** and the concepts of **autoboxing** and **unboxing**.

---

## 1. The `Object` Class

- Every class in Java implicitly extends the `Object` class if no other superclass is specified.
- Provides useful methods that can be overridden for custom behavior.

### Common Methods in `Object` Class

| Method                | Description                                                          |
|-----------------------|----------------------------------------------------------------------|
| `toString()`          | Returns a string representation of the object                        |
| `equals(Object obj)`  | Checks if two objects are "equal"                                    |
| `hashCode()`          | Returns an integer hash code for the object                          |
| `clone()`             | Creates and returns a copy of the object (needs `Cloneable` interface)|
| `getClass()`          | Returns the runtime class of the object                              |
| `finalize()`          | Called by garbage collector before destroying the object (rarely used)|

**Example:**
```java
class Person {
    String name;
    Person(String name) { this.name = name; }
    public String toString() { return "Person: " + name; }
}

public class ObjectDemo {
    public static void main(String[] args) {
        Person p = new Person("Vidvaan");
        System.out.println(p); // Calls toString()
        System.out.println(p.getClass()); // class Person
    }
}
```

---

## 2. Wrapper Classes

- Java provides **wrapper classes** for every primitive type, allowing them to be used as objects.
- Useful for working with collections (e.g., `ArrayList<Integer>`).

| Primitive | Wrapper Class |
|-----------|--------------|
| byte      | Byte         |
| short     | Short        |
| int       | Integer      |
| long      | Long         |
| float     | Float        |
| double    | Double       |
| char      | Character    |
| boolean   | Boolean      |

**Example:**
```java
int n = 10;
Integer obj = Integer.valueOf(n); // Wraps int in an Integer object
```

---

## 3. Autoboxing and Unboxing

- **Autoboxing:** Automatic conversion of a primitive to its wrapper object.
- **Unboxing:** Automatic conversion of a wrapper object to its primitive type.

**Examples:**
```java
int a = 5;
Integer obj = a;    // Autoboxing (int -> Integer)

Double dObj = 3.14; // Autoboxing (double -> Double)
double d = dObj;    // Unboxing (Double -> double)
```

---

## 4. Using Wrapper Classes with Collections

- Collections (like `ArrayList`) work with objects, not primitives.
- Wrapper classes allow primitives to be stored in collections.

**Example:**
```java
import java.util.ArrayList;

public class WrapperCollectionDemo {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();
        nums.add(10); // Autoboxing
        nums.add(20);
        int sum = nums.get(0) + nums.get(1); // Unboxing
        System.out.println(sum); // 30
    }
}
```

---

## 5. Useful Methods in Wrapper Classes

- `parseXxx(String s)` — converts string to primitive.
- `valueOf(String s)` — returns wrapper object from string.
- `xxxValue()` — gets primitive value from wrapper object.

**Example:**
```java
String s = "123";
int x = Integer.parseInt(s);          // 123 (primitive)
Integer obj = Integer.valueOf(s);     // 123 (Integer object)
int y = obj.intValue();               // 123 (primitive)
```

---

## 🎯 Task Checklist

- [x] Override `toString()` and `equals()` in your own class.
- [x] Use wrapper classes for primitives.
- [x] Practice autoboxing and unboxing.
- [x] Store primitive values in a collection (e.g., `ArrayList<Integer>`).
- [x] Use wrapper class utility methods for conversion.

---

**Great! Tomorrow you'll learn about Java Collections—`List`, `Set`, `Map`, and more.**