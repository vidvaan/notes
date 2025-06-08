# Day 3: Variables and Data Types

Welcome to Day 3! Today you'll learn about variables, primitive data types, and how to store and convert data in Java.

---

## 1. Variables in Java

A **variable** is a container for storing data values.  
Every variable in Java has a **type** (what kind of data it holds).

**Declaration and Initialization:**
```java
type variableName;              // Declaration
variableName = value;           // Initialization (assignment)

type variableName = value;      // Declaration and initialization together
```

**Example:**
```java
int age = 20;
double price = 99.99;
char grade = 'A';
boolean isJavaFun = true;
```

---

## 2. Primitive Data Types

Java has 8 built-in (primitive) data types:

| Type     | Size      | Example        | Purpose                       |
|----------|-----------|----------------|-------------------------------|
| byte     | 1 byte    | 12             | Small integers                |
| short    | 2 bytes   | 12345          | Larger integers               |
| int      | 4 bytes   | 123456         | Default integer type          |
| long     | 8 bytes   | 123456789L     | Very large integers           |
| float    | 4 bytes   | 3.14f          | Decimal numbers (less precise)|
| double   | 8 bytes   | 3.1415926      | Decimal numbers (default)     |
| char     | 2 bytes   | 'A'            | Single character              |
| boolean  | 1 bit     | true / false   | True or false                 |

**Examples:**
```java
byte smallNum = 120;
short shortNum = 32000;
int population = 1000000;
long bigNum = 1234567890L;

float temp = 36.6f;
double balance = 12345.67;

char letter = 'J';
boolean isActive = false;
```

---

## 3. Type Casting

**Type casting** is converting a value from one data type to another.

### a. Implicit (Widening) Casting  
Java will automatically convert a smaller type to a larger type:
```java
int x = 10;
double y = x;    // int to double (OK)
System.out.println(y); // 10.0
```

### b. Explicit (Narrowing) Casting  
You must specify the type when converting a larger type to a smaller type:
```java
double a = 9.8;
int b = (int) a; // Explicit cast: double to int
System.out.println(b); // 9 (fractional part lost)
```

**Examples:**
```java
int num = 150;
byte b = (byte) num; // May lose data if out of range

// float to int
float f = 4.56f;
int n = (int) f; // n = 4
```

---

## 4. Full Example

```java
public class DataTypesDemo {
    public static void main(String[] args) {
        int age = 25;           // int variable
        double salary = 50000.50; // double variable
        char grade = 'A';       // char variable
        boolean passed = true;  // boolean variable

        // Type casting
        double newSalary = age;       // Implicit (int to double)
        int roundedSalary = (int) salary; // Explicit (double to int)

        System.out.println("Age: " + age);
        System.out.println("Salary: " + salary);
        System.out.println("Grade: " + grade);
        System.out.println("Passed: " + passed);
        System.out.println("New Salary (double): " + newSalary);
        System.out.println("Rounded Salary (int): " + roundedSalary);
    }
}
```

---

## 🎯 Task Checklist

- [x] Declare and initialize variables of different primitive data types.
- [x] Practice type casting (implicit and explicit).
- [x] Write a Java program that prints different variable values.

---

**Great! Tomorrow you'll explore operators and how to perform calculations in Java.**