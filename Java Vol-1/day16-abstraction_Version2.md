# Day 16: Abstraction

Welcome to Day 16! Today, you'll learn about **abstraction** in Java—a key OOP principle for hiding details and showing only essential features. You'll discover how to use **abstract classes**, **abstract methods**, and **interfaces**.

---

## 1. What is Abstraction?

- **Abstraction** means representing only the essential details and hiding the complexity.
- In Java, abstraction is achieved via **abstract classes** and **interfaces**.

---

## 2. Abstract Classes and Methods

### a. Abstract Class

- Declared with the `abstract` keyword.
- Can have abstract (incomplete) and non-abstract (concrete) methods.
- **Cannot** be instantiated (no `new AbstractClass()`).

**Syntax:**
```java
abstract class Animal {
    abstract void makeSound(); // Abstract method (no body)
    void sleep() {             // Concrete method
        System.out.println("Sleeping...");
    }
}
```

### b. Abstract Method

- Declared without a body (ends with a semicolon).
- Subclasses **must** override all abstract methods.

---

### Example: Abstract Class

```java
abstract class Shape {
    abstract void draw(); // Abstract method

    void info() {         // Concrete method
        System.out.println("This is a shape.");
    }
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a circle.");
    }
}

public class TestAbstraction {
    public static void main(String[] args) {
        // Shape s = new Shape(); // ERROR: can't instantiate abstract class
        Shape c = new Circle();
        c.draw();   // Drawing a circle.
        c.info();   // This is a shape.
    }
}
```

---

## 3. Interfaces

- An **interface** is a collection of abstract methods (and static/final variables).
- Use `interface` keyword.
- A class "implements" an interface and provides code for its methods.
- **Supports multiple inheritance** (a class can implement several interfaces).

**Syntax:**
```java
interface Drawable {
    void draw(); // Abstract by default
}
```

### Implementing an Interface

```java
class Rectangle implements Drawable {
    public void draw() {
        System.out.println("Drawing a rectangle.");
    }
}
```

### Multiple Interfaces

```java
interface A { void foo(); }
interface B { void bar(); }

class Demo implements A, B {
    public void foo() { System.out.println("foo"); }
    public void bar() { System.out.println("bar"); }
}
```

---

## 4. Abstract Class vs Interface

| Feature           | Abstract Class         | Interface                |
|-------------------|-----------------------|--------------------------|
| Keyword           | `abstract class`      | `interface`              |
| Methods           | Both abstract/concrete| Abstract (Java 8+: default/static allowed) |
| Fields            | Instance/Static       | Public static final only |
| Inheritance       | Single (extends)      | Multiple (implements)    |
| Constructor       | Yes                   | No                       |

---

## 5. Example: Interface in Action

```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    public void makeSound() {
        System.out.println("Woof");
    }
}

public class TestInterface {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.makeSound(); // Woof
    }
}
```

---

## 🎯 Task Checklist

- [x] Create and use an abstract class and method.
- [x] Implement an interface in a class.
- [x] Demonstrate multiple interface implementation.
- [x] Summarize difference between abstract class and interface.

---

**Great job! Tomorrow you'll focus on encapsulation, getters/setters, and more.**