# Day 11: Object-Oriented Programming – Introduction

Welcome to Day 11! Today, you'll start learning **Object-Oriented Programming (OOP)** in Java by understanding **classes** and **objects**, and how to create and use them.

---

## 1. What is Object-Oriented Programming?

**OOP** is a programming paradigm based on the concept of "objects," which represent real-world entities and contain both **data** (fields/attributes) and **behavior** (methods).

**Key OOP Concepts:**  
- **Class**: Blueprint or template for objects.
- **Object**: Instance of a class.

---

## 2. Defining a Class

A **class** defines the structure and behavior of objects.

**Syntax:**
```java
class ClassName {
    // Fields (variables)
    // Methods (functions)
}
```

**Example:**
```java
class Student {
    // Fields
    String name;
    int age;

    // Method
    void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
```

---

## 3. Creating and Using Objects

- **Object**: An instance of a class made using the `new` keyword.

**Syntax:**
```java
ClassName objectName = new ClassName();
```

**Example:**
```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();        // Create object
        s1.name = "Vidvaan";               // Set fields
        s1.age = 21;

        s1.displayInfo();                  // Call method

        Student s2 = new Student();
        s2.name = "Priya";
        s2.age = 20;
        s2.displayInfo();                  // Call method for second object
    }
}
```
_Output:_
```
Name: Vidvaan, Age: 21
Name: Priya, Age: 20
```

---

## 4. Multiple Objects and Memory

- Each object has its own copy of fields.
- You can create as many objects as needed from a class.

---

## 5. Example: Simple Car Class

```java
class Car {
    String model;
    int year;

    void honk() {
        System.out.println(model + " goes beep!");
    }
}

public class TestCar {
    public static void main(String[] args) {
        Car c1 = new Car();
        c1.model = "Toyota";
        c1.year = 2022;
        c1.honk(); // Output: Toyota goes beep!
    }
}
```

---

## 🎯 Task Checklist

- [x] Define your own class with some fields and methods.
- [x] Create objects from your class and assign values to fields.
- [x] Call methods using your objects.

---

**Awesome! Tomorrow, you'll learn about constructors and the `this` keyword in Java.**