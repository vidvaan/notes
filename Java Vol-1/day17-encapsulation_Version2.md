# Day 17: Encapsulation

Welcome to Day 17! Today, you'll learn about **encapsulation**—one of the four pillars of Object-Oriented Programming (OOP). You'll understand how to hide data, use getters and setters, the difference between `this` and `super`, and the `final` keyword.

---

## 1. What is Encapsulation?

- **Encapsulation** means bundling data (fields) and methods (functions) that operate on the data into a single unit (class).
- It also means **restricting direct access** to some of the object's components, usually by making fields `private` and providing public methods to access and update them.

---

## 2. Data Hiding

- Use `private` access modifier to hide fields from outside access.
- Only allow controlled access through **getters and setters**.

**Example:**
```java
class Student {
    private String name; // hidden from outside
    private int age;

    // Getter for name
    public String getName() {
        return name;
    }
    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        if (age > 0) { // simple validation
            this.age = age;
        }
    }
}
```

---

## 3. Getters and Setters

- **Getter:** Method that returns the value of a private field.
- **Setter:** Method that sets/updates the value of a private field, sometimes with validation.

**Usage:**
```java
Student s = new Student();
s.setName("Vidvaan");
s.setAge(21);

System.out.println(s.getName()); // Vidvaan
System.out.println(s.getAge());  // 21
```

---

## 4. `this` vs `super`

### a. `this` keyword

- Refers to the **current object's** instance.
- Used to resolve ambiguity between field and parameter names, or to call other constructors in the same class.

```java
public void setName(String name) {
    this.name = name; // 'this.name' is the field, 'name' is the parameter
}
```

### b. `super` keyword

- Refers to the **parent class** instance.
- Used to access parent fields/methods or to call the parent constructor.

```java
class Person {
    String name = "Person";
}
class Student extends Person {
    String name = "Student";
    void printNames() {
        System.out.println(this.name);  // Student
        System.out.println(super.name); // Person
    }
}
```

---

## 5. The `final` Keyword

- Used to make **fields, methods, or classes unchangeable**.

| Usage             | Meaning                                                       |
|-------------------|--------------------------------------------------------------|
| `final int x;`    | Value can't be changed after initialization (constant)        |
| `final void foo()`| Method can't be overridden in subclasses                      |
| `final class A`   | Class can't be subclassed (no class can extend A)             |

**Example:**
```java
final int MAX = 100; // Can't reassign MAX

final class Constants { ... } // Can't extend Constants

class Base {
    final void show() { ... }  // Can't override in subclass
}
```

---

## 6. Complete Example

```java
class Person {
    private String name;
    private final String nationality = "Indian";

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getNationality() { return nationality; }
}

class Employee extends Person {
    private int empId;
    public int getEmpId() { return empId; }
    public void setEmpId(int empId) { this.empId = empId; }
}

public class TestEncapsulation {
    public static void main(String[] args) {
        Employee emp = new Employee();
        emp.setName("Priya");
        emp.setEmpId(102);

        System.out.println(emp.getName());         // Priya
        System.out.println(emp.getEmpId());        // 102
        System.out.println(emp.getNationality());  // Indian
    }
}
```

---

## 🎯 Task Checklist

- [x] Create a class with private fields and public getters/setters.
- [x] Demonstrate data hiding and validation using setters.
- [x] Use `this` and `super` in a subclass.
- [x] Use the `final` keyword on a field, method, and class.

---

**Nice! Tomorrow you'll learn about Java packages and organizing your code.**