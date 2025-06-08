# Day 14: Inheritance

Welcome to Day 14! Today, you'll learn about **inheritance** in Java—one of the core principles of Object-Oriented Programming (OOP). You'll explore the `extends` and `super` keywords, and method overriding.

---

## 1. What is Inheritance?

**Inheritance** lets you create a new class (child/subclass) based on an existing class (parent/superclass).  
- The child class "inherits" fields and methods from the parent class.
- Promotes code reuse and logical hierarchy.

---

## 2. The `extends` Keyword

Use `extends` to define a subclass.

**Syntax:**
```java
class Parent {
    // fields and methods
}

class Child extends Parent {
    // additional fields and methods
}
```

**Example:**
```java
class Animal {
    void eat() {
        System.out.println("Animal eats.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();  // Inherited from Animal
        d.bark(); // Defined in Dog
    }
}
```
_Output:_
```
Animal eats.
Dog barks.
```

---

## 3. The `super` Keyword

- **`super`** is used to refer to the immediate parent class.
- It can be used to:
  - Access parent class fields/methods if overridden.
  - Call the parent class constructor.

**Example:**
```java
class Animal {
    void eat() { System.out.println("Animal eats."); }
}

class Dog extends Animal {
    void eat() { System.out.println("Dog eats."); }
    void printParentEat() {
        super.eat(); // Calls Animal's eat()
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();           // Dog eats.
        d.printParentEat();// Animal eats.
    }
}
```

---

## 4. Method Overriding

- Child class can **override** (redefine) a parent class method.
- The method signature must be exactly the same in both classes.

**Example:**
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Meow");
    }
}

public class TestOverride {
    public static void main(String[] args) {
        Cat c = new Cat();
        c.sound(); // Meow
    }
}
```

---

## 5. Constructor Chaining with `super()`

- Use `super()` to call parent constructor from child constructor.

**Example:**
```java
class Animal {
    Animal() {
        System.out.println("Animal constructor");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // Calls Animal's constructor
        System.out.println("Dog constructor");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog d = new Dog();
    }
}
// Output:
// Animal constructor
// Dog constructor
```

---

## 🎯 Task Checklist

- [x] Create a parent and a child class using `extends`.
- [x] Override a method in the child class.
- [x] Use `super` to call the parent method and constructor.
- [x] Write a program that demonstrates inheritance, overriding, and use of `super`.

---

**Nice work! Tomorrow, you'll learn about encapsulation and getter/setter methods.**