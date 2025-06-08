# Day 1: Introduction to Java

Welcome to Day 1 of your Core Java journey! Today you'll get a big-picture view of Java, set up your environment, and write your very first Java program.

---

## 1. What is Java?

Java is a **high-level, object-oriented, platform-independent programming language** developed by Sun Microsystems (now Oracle) in 1995.

### History
- **Created by:** James Gosling and team at Sun Microsystems, released in 1995.
- **Philosophy:** "Write Once, Run Anywhere"—Java code runs on any device with a Java Virtual Machine (JVM).

### Features
- Simple, easy to learn
- Object-Oriented
- Platform independent (via JVM)
- Secure and robust
- Multithreaded and dynamic
- Rich standard library

### JVM, JRE, JDK
- **JVM (Java Virtual Machine):** Runs Java bytecode, platform-dependent implementation.
- **JRE (Java Runtime Environment):** JVM + core libraries, used to run Java applications.
- **JDK (Java Development Kit):** JRE + development tools (compiler, debugger, etc.), used to develop Java programs.

---

## 2. Setting up Java

### a. Install Java (JDK)
- Go to [Oracle JDK Downloads](https://www.oracle.com/java/technologies/downloads/) or use [OpenJDK](https://adoptopenjdk.net/).
- Download and install the latest JDK for your OS.
- Verify installation:
  ```sh
  java -version
  javac -version
  ```
  Both commands should display installed version numbers.

### b. Choose an IDE or Editor
- Popular IDEs: IntelliJ IDEA, Eclipse, NetBeans
- Or use a simple editor (VS Code, Sublime Text, etc.)

---

## 3. Your First Java Program: "Hello World"

### Step 1: Create the Source File

Create a file named `HelloWorld.java`:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Step 2: Compile the Program

Open a terminal/command prompt, navigate to the file's directory, and run:

```sh
javac HelloWorld.java
```
This creates a `HelloWorld.class` file (bytecode).

### Step 3: Run the Program

```sh
java HelloWorld
```
You should see:
```
Hello, World!
```

---

## 4. Recap

- Java is platform-independent and widely used.
- You need the JDK to write and run Java code.
- Java programs are written in `.java` files, compiled to `.class` files, and run on the JVM.
- You wrote and ran your first Java program!

---

## 🎯 Task Checklist

- [x] Learn what Java is and its main features.
- [x] Install the JDK and set up your development environment.
- [x] Write, compile, and run "Hello, World!" in Java.

---

**Great job! Tomorrow you’ll dive into the structure of a Java program and understand its building blocks.**