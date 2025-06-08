# Day 5: Input and Output

Welcome to Day 5! Today, you'll learn how to **get input from the user** using `Scanner` and **display output** with `System.out.println()` in Java.

---

## 1. Output: Printing with `System.out.println()`

Use `System.out.println()` to print text or variables to the console.

**Example:**
```java
System.out.println("Hello, Java!"); // Prints a line of text

int age = 20;
System.out.println("Age: " + age);  // Prints text and variable value
```

- Use `System.out.print()` if you **don't** want a new line after printing.

---

## 2. Input: Using `Scanner` for User Input

Java does not have a built-in function like Python's `input()`. Instead, you use the `Scanner` class from `java.util` package.

### a. Import Scanner

Add this line at the top of your file:
```java
import java.util.Scanner;
```

### b. Create a Scanner Object

```java
Scanner sc = new Scanner(System.in);
```

### c. Reading Different Types of Input

| Method                | Reads         | Example                                                    |
|-----------------------|--------------|------------------------------------------------------------|
| `nextLine()`          | Line (String)| `String name = sc.nextLine();`                             |
| `nextInt()`           | Integer      | `int age = sc.nextInt();`                                  |
| `nextDouble()`        | Double       | `double salary = sc.nextDouble();`                         |
| `next()`              | Word (String)| `String word = sc.next();`                                 |

---

## 3. Example: Input and Output Program

```java
import java.util.Scanner;

public class InputOutputDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Getting a string input
        System.out.print("Enter your name: ");
        String name = sc.nextLine();

        // Getting an integer input
        System.out.print("Enter your age: ");
        int age = sc.nextInt();

        // Getting a double input
        System.out.print("Enter your height (in cm): ");
        double height = sc.nextDouble();

        System.out.println();
        System.out.println("Hello, " + name + "!");
        System.out.println("You are " + age + " years old and " + height + " cm tall.");
        
        sc.close(); // Always close the scanner when done
    }
}
```

**Sample Output:**
```
Enter your name: Vidvaan
Enter your age: 21
Enter your height (in cm): 175.5

Hello, Vidvaan!
You are 21 years old and 175.5 cm tall.
```

---

## 4. Tips

- Always import `java.util.Scanner`.
- Close the `Scanner` with `sc.close()` when done (especially in larger programs).
- Be careful mixing `nextInt()`, `nextDouble()`, and `nextLine()`—sometimes `nextLine()` may read the leftover newline. If that happens, read the leftover line with an extra `sc.nextLine()`.

---

## 🎯 Task Checklist

- [x] Use `System.out.println()` to print output.
- [x] Read user input with `Scanner`.
- [x] Write a program that asks for the user's name, age, and favorite number, then prints a summary.

---

**Great job! Tomorrow you'll learn about control flow: if/else and switch statements.**