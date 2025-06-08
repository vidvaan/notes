# Day 18: Packages

Welcome to Day 18! Today you'll learn about **packages** in Java—how to create, use, and import them. Packages help organize your code into namespaces, prevent naming conflicts, and make large projects manageable.

---

## 1. What is a Package?

- A **package** is a namespace that organizes related classes and interfaces.
- Java's standard library uses packages (e.g., `java.util`, `java.io`).
- Your own packages help structure your code and avoid class name conflicts.

---

## 2. Creating a Package

- Use the `package` keyword at the top of your Java file.
- The file should be placed in a folder matching the package name.

**Example:**
```
project/
  └── mypackage/
        └── MyClass.java
```
```java
// File: mypackage/MyClass.java
package mypackage;

public class MyClass {
    public void show() {
        System.out.println("Hello from MyClass in mypackage!");
    }
}
```

---

## 3. Using and Importing Packages

To use a class from another package, use the `import` statement.

**Example:**
```java
// File: TestPackage.java (in the root project folder)
import mypackage.MyClass;

public class TestPackage {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.show();
    }
}
```

- `import packageName.ClassName;` imports a single class.
- `import packageName.*;` imports all classes in the package.

---

## 4. Default Package

- If you don't specify a package, your class is in the "default package."
- It's best practice to always use named packages for larger projects.

---

## 5. Access Modifiers with Packages

- `public` classes/methods are accessible from outside the package.
- Default (no modifier) members are **package-private** (only accessible within the same package).

---

## 6. Example: Step-by-Step

**Step 1: Create a package and class**
```java
// File: shapes/Circle.java
package shapes;

public class Circle {
    public double radius;
    public Circle(double r) { radius = r; }
    public double area() { return Math.PI * radius * radius; }
}
```

**Step 2: Use this class in another file**
```java
// File: TestShapes.java
import shapes.Circle;

public class TestShapes {
    public static void main(String[] args) {
        Circle c = new Circle(5);
        System.out.println("Area: " + c.area());
    }
}
```

**Step 3: Compile and Run**
```bash
# Compile (from root project directory)
javac shapes/Circle.java
javac TestShapes.java

# Run
java TestShapes
```

---

## 7. Java Standard Packages

- Common built-in packages:
  - `java.lang` (automatically imported): String, Math, System, etc.
  - `java.util`: Scanner, ArrayList, HashMap, etc.
  - `java.io`: File, InputStream, OutputStream, etc.

---

## 🎯 Task Checklist

- [x] Create a custom package and add a class to it.
- [x] Use `import` to access your class from another file.
- [x] Understand package-private vs public members.
- [x] Explore standard Java packages and use at least one (e.g. `java.util.Scanner`).

---

**Great! Tomorrow you'll learn about exception handling in Java.**