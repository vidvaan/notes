# Day 10: Queue & Deque

Today you'll explore the Queue and Deque (Double-Ended Queue) interfaces in Java, their key implementations, and common use cases.

---

## Queue Interface

- Models a **First-In-First-Out (FIFO)** data structure.
- Common operations: `offer()` (add), `poll()` (remove), `peek()` (view front), `isEmpty()`.

### Main Implementations

#### 1. **LinkedList as Queue**
- `LinkedList` implements the `Queue` interface.
- Can be used as a FIFO queue (also as Deque).
```java
Queue<String> queue = new LinkedList<>();
queue.offer("Task1");
queue.offer("Task2");
System.out.println(queue.poll()); // Task1
```

#### 2. **PriorityQueue**
- Elements are ordered according to natural ordering or a custom `Comparator`.
- Not strictly FIFO: elements with **highest priority come out first**.
- No null elements allowed.
```java
Queue<Integer> pq = new PriorityQueue<>();
pq.offer(3);
pq.offer(1);
pq.offer(2);
System.out.println(pq.poll()); // 1 (smallest comes out first)
```

---

## Deque Interface

- **Double-Ended Queue**: supports insertion/removal at both ends (FIFO or LIFO).
- Common methods: `addFirst()`, `addLast()`, `removeFirst()`, `removeLast()`, `peekFirst()`, `peekLast()`.

### Main Implementations

#### 1. **ArrayDeque**
- Resizable-array implementation of Deque.
- Faster than `LinkedList` for stack/queue operations.
- No capacity restrictions (unless explicitly specified).
- No null elements allowed.
```java
Deque<String> deque = new ArrayDeque<>();
deque.addFirst("A");
deque.addLast("B");
System.out.println(deque.removeFirst()); // A
System.out.println(deque.removeLast());  // B
```

#### 2. **LinkedList as Deque**
- `LinkedList` also implements `Deque`.
- Allows efficient insertion/removal at both ends.

---

## Use Cases

- **Task Scheduling:** Queue up tasks, process them in order (e.g., print jobs, thread pools).
- **Buffering:** Temporary storage of data (e.g., file reading buffers, network packet queues).
- **Undo/Redo Functionality:** Deque used for both stack (undo) and queue (redo) operations.
- **Priority Handling:** Use `PriorityQueue` for tasks that must be handled out of order (e.g., emergency requests).

---

## Summary Table

| Interface   | Implementation   | FIFO/LIFO   | Ordering            | Nulls | Use Case                          |
|-------------|------------------|-------------|---------------------|-------|-----------------------------------|
| Queue       | LinkedList       | FIFO        | Insertion           | Yes   | General queue, buffer             |
| Queue       | PriorityQueue    | FIFO (sort) | Priority            | No    | Task scheduling, simulation       |
| Deque       | ArrayDeque       | Both        | Insertion           | No    | Stack (LIFO), queue (FIFO), undo  |
| Deque       | LinkedList       | Both        | Insertion           | Yes   | Stack/queue, double-ended buffer  |

---

## Practice

- Create a task queue using `LinkedList` and process items in order.
- Use a `PriorityQueue` for jobs with priorities.
- Implement an undo/redo feature with `ArrayDeque`.

---