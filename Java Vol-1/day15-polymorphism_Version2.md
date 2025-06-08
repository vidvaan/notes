# Day 15: Polymorphism

Welcome to Day 15! Today, you'll learn about **polymorphism** in Java, which means "many forms". Polymorphism allows objects to take on more than one form depending on context—making code flexible and extensible.

---

## 1. What is Polymorphism?

**Polymorphism** enables the same method or object to behave differently in different contexts:
- **Compile-time polymorphism:** Achieved by method overloading.
- **Runtime polymorphism:** Achieved by method overriding and dynamic method dispatch.

---

## 2. Compile-time Polymorphism (Method Overloading)

- **Method overloading**: Multiple methods have the same name but different parameter lists (number, type, or order).
- The method to call is determined at **compile time**.

**Example:**
```java
class MathUtils {
    int add(int a, int b) {
        return a + b;
    }
    double add(double a, double b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class TestOverloading {
    public static void main(String[] args) {
        MathUtils m = new MathUtils();
        System.out.println(m.add(2, 3));          // 5
        System.out.println(m.add(2.5, 3.1));      // 5.6
        System.out.println(m.add(1, 2, 3));       // 6
    }
}
```

---

## 3. Runtime Polymorphism (Method Overriding & Dynamic Method Dispatch)

- **Method overriding**: Subclass provides a specific implementation for a method already defined in its superclass.
- The method that's actually called is determined at **runtime** (dynamic method dispatch).

### a. Example of Runtime Polymorphism

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Woof");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Meow");
    }
}

public class TestPolymorphism {
    public static void main(String[] args) {
        Animal a;

        a = new Dog();
        a.sound(); // Woof

        a = new Cat();
        a.sound(); // Meow
    }
}
```

### b. Dynamic Method Dispatch

- When a superclass reference refers to a subclass object, and you call an overridden method, the **subclass's method** executes.
- This is called **dynamic method dispatch**.

---

## 4. Why Use Polymorphism?

- Write flexible and extensible code.
- Treat objects of different subclasses in a uniform way.
- Add new behavior with minimal changes to existing code.

---

## 5. Example: Shape Area Calculation

```java
class Shape {
    void area() {
        System.out.println("Calculating area...");
    }
}

class Circle extends Shape {
    @Override
    void area() {
        System.out.println("Area of circle: πr^2");
    }
}

class Rectangle extends Shape {
    @Override
    void area() {
        System.out.println("Area of rectangle: l*w");
    }
}

public class TestShapes {
    public static void main(String[] args) {
        Shape s;

        s = new Circle();
        s.area(); // Area of circle: πr^2

        s = new Rectangle();
        s.area(); // Area of rectangle: l*w
    }
}
```

---

## 🎯 Task Checklist

- [x] Create overloaded methods (compile-time polymorphism).
- [x] Override a method in a subclass and demonstrate runtime polymorphism.
- [x] Use a superclass reference to refer to different subclass objects and call overridden methods (dynamic method dispatch).

---

**Great job! Next, you'll learn about abstraction and interfaces in Java.**