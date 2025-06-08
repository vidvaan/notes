# Day 23: Multithreading Basics

Welcome to Day 23! Today, you'll learn about **multithreading**—the ability for a program to execute multiple threads (lightweight processes) simultaneously. You’ll learn how to create threads using the `Thread` class and the `Runnable` interface, and understand the thread lifecycle.

---

## 1. What is Multithreading?

- **Multithreading** allows programs to perform multiple tasks concurrently.
- Each thread runs independently, sharing process resources.
- Useful for tasks like parallel computations, handling user interfaces, or background tasks.

---

## 2. Creating Threads

### a. By Extending the `Thread` Class

**Steps:**
1. Create a class that extends `Thread`.
2. Override the `run()` method.
3. Create an object & call `start()` (not `run()` directly!).

**Example:**
```java
class MyThread extends Thread {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Thread running: " + i);
        }
    }
}

public class ThreadDemo1 {
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start(); // Starts a new thread, calls run()
    }
}
```

---

### b. By Implementing the `Runnable` Interface

**Steps:**
1. Create a class that implements `Runnable`.
2. Implement the `run()` method.
3. Pass an instance to a `Thread` object and call `start()`.

**Example:**
```java
class MyRunnable implements Runnable {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Runnable running: " + i);
        }
    }
}

public class ThreadDemo2 {
    public static void main(String[] args) {
        MyRunnable r = new MyRunnable();
        Thread t = new Thread(r);
        t.start();
    }
}
```

---

## 3. Thread Lifecycle

A thread typically passes through these states:

1. **New**: Thread object created, not started yet.
2. **Runnable**: `start()` called; ready to run or running.
3. **Running**: Actually executing its `run()` method.
4. **Blocked/Waiting**: Waiting for resources or another thread.
5. **Terminated/Dead**: `run()` method completed or thread stopped.

![Thread Lifecycle Diagram](https://i.imgur.com/ljtBIVn.png)

---

## 4. Main Thread

- The thread that runs the `main()` method is called the **main thread**.
- You can run multiple threads in parallel with the main thread.

---

## 5. Example: Multiple Threads

```java
class Counter extends Thread {
    public void run() {
        for (int i = 1; i <= 3; i++) {
            System.out.println(getName() + ": " + i);
        }
    }
}

public class MultiThreadDemo {
    public static void main(String[] args) {
        Counter t1 = new Counter();
        Counter t2 = new Counter();
        t1.start();
        t2.start();
        System.out.println("Main thread finished!");
    }
}
```
_Output may vary as threads run independently._

---

## 6. Key Points

- Always call `start()` to run a thread (not `run()` directly).
- Threads may overlap in output—order is not guaranteed!
- You can also use lambda expressions with Runnable (Java 8+):

```java
Thread t = new Thread(() -> {
    System.out.println("Lambda thread!");
});
t.start();
```

---

## 🎯 Task Checklist

- [x] Create a thread by extending `Thread`.
- [x] Create a thread by implementing `Runnable`.
- [x] Start multiple threads and observe output.
- [x] Draw or review the thread lifecycle diagram.

---

**Great! Tomorrow, you'll learn about synchronization and inter-thread communication.**