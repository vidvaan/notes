# Day 14: Introduction to Java 8 Features

Java 8 introduced powerful new features that make coding more expressive, concise, and enable functional programming in Java. Today you’ll learn **why** these features were added, what they are, and focus on the enhancements to interfaces.

---

## 1. Motivation for Java 8 Features

- **Modern Programming Needs:** Developers wanted more concise, expressive, and functional programming styles (like in Scala, Python).
- **Parallelism:** Need for easy data processing in parallel (multi-core CPUs).
- **Easier API Design:** Enable more flexible, backward-compatible APIs.

---

## 2. Java 8 Key Features Overview

- **Default and Static Methods in Interfaces:** Interfaces can now have concrete methods.
- **Lambda Expressions:** Concise way to write instances of single-method interfaces.
- **Streams API:** Process collections in a functional, pipeline style.
- **Functional Interfaces:** Interfaces with a single abstract method, target type for lambdas/method references.
- **New Date/Time API:** Modern, immutable, thread-safe alternatives to `Date` and `Calendar`.

---

## 3. Default and Static Methods in Interfaces

### a. Default Methods

- Allow interfaces to have methods with a default implementation.
- Helps in evolving APIs without breaking existing implementations.

**Syntax:**
```java
interface MyInterface {
    void show();
    default void print() {
        System.out.println("Default implementation");
    }
}
```

### b. Static Methods

- Interfaces can declare static methods (utility/helper methods).

**Syntax:**
```java
interface MyInterface {
    static void display() {
        System.out.println("Static method in interface");
    }
}
```

### c. Why Are These Useful?

- You can add new behaviors to interfaces without forcing all implementing classes to override them.
- Enables richer, more maintainable libraries and APIs.

---

## 4. Example: Default and Static Methods

```java
interface Vehicle {
    void drive();

    default void honk() {
        System.out.println("Honking!");
    }

    static void info() {
        System.out.println("All vehicles have wheels.");
    }
}

class Car implements Vehicle {
    public void drive() {
        System.out.println("Car is driving.");
    }
    // Optionally override honk()
}

public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.drive();         // Car is driving.
        c.honk();          // Honking!
        Vehicle.info();    // All vehicles have wheels.
    }
}
```

---

## 5. What's Next?

- **Lambdas**: Anonymous functions for concise code.
- **Streams**: Data processing pipelines.
- **Functional Interfaces**: Foundation for lambdas.
- **New Date/Time API**: Easier, safer date/time handling.

---

## 🎯 Task Checklist

- [x] Read about the motivation for Java 8 features.
- [x] Write an interface with default and static methods.
- [x] Use these methods in a class.
- [x] Think of how these new features make Java APIs better.

---

**Next: Dive deeper into Lambda Expressions and Functional Interfaces!**