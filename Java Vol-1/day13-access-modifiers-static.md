# Day 13: Access Modifiers & Static Keyword

Welcome to Day 13! Today you'll learn about **access modifiers** (which control visibility of classes, variables, and methods) and the **static** keyword (for class-level variables and methods).

---

## 1. Access Modifiers

Access modifiers determine the visibility (scope) of classes, fields, methods, and constructors.

| Modifier   | Accessible within class | Accessible in same package | Accessible in subclass | Accessible everywhere |
|------------|:----------------------:|:-------------------------:|:---------------------:|:--------------------:|
| `public`   | ✔                      | ✔                        | ✔                    | ✔                   |
| `protected`| ✔                      | ✔                        | ✔                    | ✗                   |
| (default)* | ✔                      | ✔                        | ✗                    | ✗                   |
| `private`  | ✔                      | ✗                        | ✗                    | ✗                   |

> *Default (no modifier) is also called "package-private".

### Examples

```java
public class MyClass {
    public int a;        // Accessible everywhere
    protected int b;     // Accessible in package & subclasses
    int c;               // Default: accessible in package
    private int d;       // Only accessible in MyClass
}
```

---

## 2. Static Variables and Methods

The `static` keyword makes a **variable or method belong to the class itself**, not just to instances (objects) of the class.

### a. Static Variables (Class Variables)

- Shared by all objects of the class.
- Useful for values common to all instances.

**Example:**
```java
class Counter {
    static int count = 0;      // Static variable

    Counter() {
        count++;
    }
}

public class Test {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        System.out.println(Counter.count); // 2
    }
}
```

### b. Static Methods

- Can be called **without creating an object**.
- Only access static variables or call other static methods (can’t use non-static fields).

**Example:**
```java
class MathUtils {
    static int square(int x) {
        return x * x;
    }
}

public class TestMath {
    public static void main(String[] args) {
        System.out.println(MathUtils.square(5)); // 25
    }
}
```

---

## 3. Example: Static vs Non-static

```java
class Example {
    static int staticVar = 10;
    int instanceVar = 20;

    static void staticMethod() {
        System.out.println("StaticVar = " + staticVar);
        // System.out.println(instanceVar); // ERROR: Cannot access non-static from static
    }

    void instanceMethod() {
        System.out.println("StaticVar = " + staticVar);
        System.out.println("InstanceVar = " + instanceVar);
    }
}
```

---

## 4. Summary Table

| Keyword     | Used for           | Accessed by               | Can access non-static? | Example call              |
|-------------|--------------------|---------------------------|------------------------|---------------------------|
| `public`    | All                | Anywhere                  | Yes                    | `obj.publicMethod()`      |
| `private`   | Inside class only  | Only within class         | Yes                    | `privateVar`              |
| `protected` | Package + subclass | Same package/subclass     | Yes                    | `protectedMethod()`       |
| (default)   | Package only       | Same package              | Yes                    | `defaultVar`              |
| `static`    | Class-level        | `ClassName.staticMember`  | No                     | `ClassName.staticMethod()`|

---

## 🎯 Task Checklist

- [x] Practice all four access modifiers in code.
- [x] Create and use static variables and methods.
- [x] Write a class that counts how many objects have been created using a static variable.

---

**Great progress! Tomorrow you'll learn about encapsulation and getter/setter methods.**