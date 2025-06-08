# Day 10: Methods

Welcome to Day 10! Today you'll learn about **methods** in Java—how to define, call, and overload them. Methods help organize your code, avoid repetition, and make programs easier to read and maintain.

---

## 1. What is a Method?

A **method** is a block of code that performs a specific task.  
It can take inputs (parameters), do some processing, and optionally return a value.

---

## 2. Defining a Method

**Syntax:**
```java
returnType methodName(parameter1Type param1, parameter2Type param2, ...) {
    // method body
    // optional: return value;
}
```

- `returnType`: The type of value the method returns (`void` if nothing)
- `methodName`: The name you give your method (should follow camelCase)
- `parameters`: Optional inputs (can be zero or more)

**Example 1: A method with no parameters and no return value**
```java
void sayHello() {
    System.out.println("Hello!");
}
```

**Example 2: A method with parameters and a return value**
```java
int add(int a, int b) {
    return a + b;
}
```

---

## 3. Calling a Method

- From inside the same class, just use the method name:
    ```java
    sayHello();
    int sum = add(5, 3);
    System.out.println(sum); // 8
    ```
- If the method is `static`, call it with the class name:
    ```java
    Math.sqrt(16); // Static method from Math class
    ```

---

## 4. Method Parameters and Return Types

- **Parameters** are values you pass in when calling a method.
- **Return type** is the type of value the method gives back.

**Example:**
```java
public static int multiply(int x, int y) {
    return x * y;
}
```
Call it like:
```java
int result = multiply(4, 5); // result is 20
```

---

## 5. Method Overloading

**Method overloading** is when you define multiple methods with the same name but different parameter lists. The compiler decides which one to use based on the arguments you provide.

**Example:**
```java
void print(String s) {
    System.out.println(s);
}

void print(int n) {
    System.out.println(n);
}

void print(String s, int n) {
    System.out.println(s + " " + n);
}
// All three 'print' methods are overloaded!
```

---

## 6. Complete Example

```java
public class MethodDemo {
    // Method with no parameters and no return value
    static void greet() {
        System.out.println("Welcome!");
    }

    // Method with parameters and a return value
    static int add(int a, int b) {
        return a + b;
    }

    // Overloaded methods
    static double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        greet();
        int sum1 = add(5, 7);
        double sum2 = add(4.5, 6.2);

        System.out.println("Sum1: " + sum1);
        System.out.println("Sum2: " + sum2);
    }
}
```

_Output:_
```
Welcome!
Sum1: 12
Sum2: 10.7
```

---

## 🎯 Task Checklist

- [x] Define and call methods with and without parameters.
- [x] Use return values from methods.
- [x] Create overloaded methods with the same name but different parameter lists.
- [x] Write a simple calculator program using methods for different operations.

---

**Keep going! Tomorrow, you'll learn the basics of Object-Oriented Programming (OOP) in Java.**