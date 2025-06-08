# Day 12: Constructors

Welcome to Day 12! Today, you'll learn about **constructors** in Java—special methods used to initialize objects. You'll explore default and parameterized constructors, as well as constructor overloading.

---

## 1. What is a Constructor?

A **constructor** is a special method called when an object is created.
- It has the same name as the class.
- It has **no return type** (not even `void`).
- Its purpose: **initialize object fields**.

---

## 2. Default Constructor

If you don't write any constructor, Java provides a **default constructor** (no parameters), which assigns default values to all fields.

**Example:**
```java
class Book {
    String title;
    int year;
    // No constructor written, so there is an implicit default constructor
}

public class Main {
    public static void main(String[] args) {
        Book b = new Book();         // Calls default constructor
        System.out.println(b.title); // null
        System.out.println(b.year);  // 0
    }
}
```

You can also define your own default constructor:
```java
class Book {
    String title;
    int year;
    // Default constructor
    Book() {
        title = "Unknown";
        year = 2000;
    }
}
```

---

## 3. Parameterized Constructor

A **parameterized constructor** lets you set values while creating the object.

**Example:**
```java
class Book {
    String title;
    int year;
    // Parameterized constructor
    Book(String t, int y) {
        title = t;
        year = y;
    }
}

public class Main {
    public static void main(String[] args) {
        Book b = new Book("Java Basics", 2022);
        System.out.println(b.title); // Java Basics
        System.out.println(b.year);  // 2022
    }
}
```

---

## 4. Constructor Overloading

You can have **multiple constructors** in a class, as long as their parameters are different—this is called **constructor overloading**.

**Example:**
```java
class Book {
    String title;
    int year;

    // Default constructor
    Book() {
        title = "Unknown";
        year = 2000;
    }

    // Parameterized constructor
    Book(String t, int y) {
        title = t;
        year = y;
    }
}

public class Main {
    public static void main(String[] args) {
        Book b1 = new Book();                     // Uses default constructor
        Book b2 = new Book("OOP in Java", 2023);  // Uses parameterized
        System.out.println(b1.title + ", " + b1.year); // Unknown, 2000
        System.out.println(b2.title + ", " + b2.year); // OOP in Java, 2023
    }
}
```

---

## 5. Using `this` Keyword

Use `this` to refer to the current object's fields (useful when parameter and field names are the same):

```java
class Student {
    String name;
    int age;
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

---

## 🎯 Task Checklist

- [x] Create a class with both default and parameterized constructors.
- [x] Practice constructor overloading.
- [x] Use `this` keyword to distinguish fields from parameters.
- [x] Create objects using different constructors and print their details.

---

**Awesome! Tomorrow, you'll learn about the four pillars of OOP: inheritance, encapsulation, polymorphism, and abstraction.**