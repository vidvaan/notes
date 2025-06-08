# Day 9: Strings

Welcome to Day 9! Today, you'll learn about **Strings** in Java: the `String` class, how to create and use Strings, and explore common methods to manipulate text.

---

## 1. What is a String?

A **String** is a sequence of characters, like `"Hello"`, `"Java123"`, or `"A"`.  
In Java, Strings are objects of the `String` class (not primitive types).

---

## 2. Creating Strings

**Two common ways:**
```java
String name = "Vidvaan";           // String literal (recommended)
String city = new String("Delhi"); // Using constructor (less common)
```

---

## 3. String Immutability

Strings in Java are **immutable** – once created, they cannot be changed.  
Any modification creates a new String object.

---

## 4. Common String Methods

Here are some useful methods from the `String` class:

| Method                        | Example                                | Output                    |
|-------------------------------|----------------------------------------|---------------------------|
| `length()`                    | `"Java".length()`                      | `4`                       |
| `charAt(index)`               | `"Java".charAt(2)`                     | `'v'`                     |
| `substring(begin, end)`       | `"Java".substring(1,3)`                | `"av"`                    |
| `concat(str)`                 | `"Java".concat("Script")`              | `"JavaScript"`            |
| `toLowerCase()`               | `"Hello".toLowerCase()`                | `"hello"`                 |
| `toUpperCase()`               | `"Hello".toUpperCase()`                | `"HELLO"`                 |
| `equals(str)`                 | `"hi".equals("hi")`                    | `true`                    |
| `equalsIgnoreCase(str)`       | `"hi".equalsIgnoreCase("HI")`          | `true`                    |
| `contains(str)`               | `"apple".contains("pp")`               | `true`                    |
| `replace(old, new)`           | `"apple".replace('p', 'b')`            | `"abble"`                 |
| `trim()`                      | `"  hi  ".trim()`                      | `"hi"`                    |
| `split(delimiter)`            | `"a,b,c".split(",")`                   | `{"a","b","c"}`           |

---

## 5. Example: Using String Methods

```java
public class StringDemo {
    public static void main(String[] args) {
        String str = "  Hello, Java!  ";
        System.out.println("Original: '" + str + "'");
        System.out.println("Trimmed: '" + str.trim() + "'");
        System.out.println("Length: " + str.length());
        System.out.println("Uppercase: " + str.toUpperCase());
        System.out.println("Substring (7,11): " + str.substring(7, 11)); // "Java"
        System.out.println("First char: " + str.charAt(2));
        System.out.println("Replace: " + str.replace("Java", "World"));
        
        // Splitting
        String csv = "apple,banana,grape";
        String[] fruits = csv.split(",");
        for(String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

---

## 6. String Comparison

- Use `.equals()` to compare string values (not `==`).
- `==` checks if objects are the same in memory, **not** their contents.

**Example:**
```java
String a = "hi";
String b = "hi";
String c = new String("hi");

System.out.println(a == b);        // true (string pool)
System.out.println(a == c);        // false (different object)
System.out.println(a.equals(c));   // true (same value)
```

---

## 🎯 Task Checklist

- [x] Create and print Strings.
- [x] Use at least 5 different String methods.
- [x] Write a program that splits a sentence into words and prints each word.

---

**Great progress! Tomorrow you'll dive into defining and using methods in Java.**