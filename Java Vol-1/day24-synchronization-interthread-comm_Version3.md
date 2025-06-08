# Day 24: Synchronization and Inter-thread Communication

Welcome to Day 24! Today you'll learn how to coordinate multiple threads using **synchronization** and how threads can communicate with each other using `wait()`, `notify()`, and `notifyAll()` in Java.

---

## 1. Why Synchronization?

- When multiple threads access shared resources, data inconsistency can occur (race conditions).
- **Synchronization** ensures that only one thread can access a resource at a time.

---

## 2. The `synchronized` Keyword

- Used to lock a method or block of code so only one thread can execute it at a time.
- Can be used on methods or code blocks.

### a. Synchronized Method

```java
public synchronized void increment() {
    count++;
}
```

### b. Synchronized Block

```java
public void increment() {
    synchronized(this) {
        count++;
    }
}
```
- Here, `this` is the lock object. You can also use any other object as a lock.

---

## 3. Example: Without and With Synchronization

**Without synchronization:**
```java
class Counter {
    int count = 0;
    void increment() { count++; }
}
```
Multiple threads can cause incorrect `count` value.

**With synchronization:**
```java
class Counter {
    int count = 0;
    synchronized void increment() { count++; }
}
```
Now, only one thread at a time can execute `increment()`.

---

## 4. Inter-thread Communication: `wait()`, `notify()`, `notifyAll()`

- These methods are used for communication between threads.
- All three are called on objects, not threads, and must be used inside synchronized blocks/methods.

| Method      | Description                                             |
|-------------|--------------------------------------------------------|
| `wait()`    | Releases the lock and waits until notified             |
| `notify()`  | Wakes up a single waiting thread                       |
| `notifyAll()` | Wakes up all waiting threads                        |

---

### Example: Producer-Consumer Problem

```java
class Shared {
    int data;
    boolean available = false;

    synchronized void produce(int value) {
        while (available) {
            try { wait(); } catch (InterruptedException e) {}
        }
        data = value;
        available = true;
        System.out.println("Produced: " + data);
        notify();
    }

    synchronized int consume() {
        while (!available) {
            try { wait(); } catch (InterruptedException e) {}
        }
        available = false;
        System.out.println("Consumed: " + data);
        notify();
        return data;
    }
}

class Producer extends Thread {
    Shared shared;
    Producer(Shared s) { shared = s; }
    public void run() {
        for (int i = 1; i <= 5; i++) shared.produce(i);
    }
}

class Consumer extends Thread {
    Shared shared;
    Consumer(Shared s) { shared = s; }
    public void run() {
        for (int i = 1; i <= 5; i++) shared.consume();
    }
}

public class ProducerConsumerDemo {
    public static void main(String[] args) {
        Shared shared = new Shared();
        new Producer(shared).start();
        new Consumer(shared).start();
    }
}
```

---

## 5. Rules for Using `wait()`, `notify()`, `notifyAll()`

- Must be called from within a synchronized context.
- `wait()` releases the lock; `notify()` and `notifyAll()` do not release the lock immediately.
- Use `while` (not `if`) to avoid spurious wakeups.

---

## 6. Summary Table

| Feature         | Purpose                                 |
|-----------------|-----------------------------------------|
| `synchronized`  | Mutual exclusion for shared resources   |
| `wait()`        | Make thread wait for a condition        |
| `notify()`      | Wake up one waiting thread              |
| `notifyAll()`   | Wake up all waiting threads             |

---

## 🎯 Task Checklist

- [x] Write a synchronized method and block.
- [x] Practice using `wait()`, `notify()`, and `notifyAll()`.
- [x] Solve a producer-consumer or similar problem using inter-thread communication.

---

**Awesome! Next, you'll learn about lambda expressions and functional interfaces.**