# Day 26: Useful Java APIs

Welcome to Day 26! Today you'll explore some of the most **useful built-in Java APIs**: `Math`, `Arrays`, `StringBuffer`, `StringBuilder`, and the Date/Time API. These classes and utilities make everyday coding in Java faster and easier.

---

## 1. Math Class

The `java.lang.Math` class provides common mathematical operations.

**Common methods:**
- `Math.abs(x)` — Absolute value
- `Math.max(a, b)` / `Math.min(a, b)`
- `Math.pow(a, b)` — a to the power of b
- `Math.sqrt(x)` — Square root
- `Math.random()` — Random double [0.0, 1.0)
- `Math.round(x)`, `Math.ceil(x)`, `Math.floor(x)` — Rounding

**Example:**
```java
System.out.println(Math.abs(-5));           // 5
System.out.println(Math.max(10, 20));       // 20
System.out.println(Math.pow(2, 3));         // 8.0
System.out.println(Math.sqrt(16));          // 4.0
System.out.println(Math.round(5.4));        // 5
System.out.println(Math.random());          // e.g., 0.727...
```

---

## 2. Arrays Class

The `java.util.Arrays` class contains utility methods for arrays.

**Common methods:**
- `Arrays.sort(array)` — Sorts the array
- `Arrays.toString(array)` — Converts array to readable string
- `Arrays.equals(arr1, arr2)` — Checks if arrays are equal
- `Arrays.fill(array, value)` — Fills array with a value
- `Arrays.copyOf(array, newLength)` — Copies an array

**Example:**
```java
import java.util.Arrays;

int[] nums = {3, 1, 4, 2};
Arrays.sort(nums);                          // [1, 2, 3, 4]
System.out.println(Arrays.toString(nums));  // [1, 2, 3, 4]
int[] nums2 = Arrays.copyOf(nums, 6);      // [1, 2, 3, 4, 0, 0]
```

---

## 3. StringBuffer and StringBuilder

Both are mutable versions of `String`.  
- **StringBuffer** is thread-safe (synchronized).  
- **StringBuilder** is faster, but not thread-safe.

**Common methods:**
- `append(str)` — Adds to end
- `insert(pos, str)` — Inserts at position
- `reverse()` — Reverses the contents
- `delete(start, end)` — Removes substring
- `toString()` — Converts to String

**Example:**
```java
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");
sb.insert(0, "Say: ");
sb.reverse();
System.out.println(sb); // Output is reversed!

StringBuilder sb2 = new StringBuilder("Java");
sb2.append(" Rocks!");
System.out.println(sb2); // Java Rocks!
```

---

## 4. Date/Time API

### a. Old Date API (`java.util.Date`, `java.util.Calendar`)
- Outdated, avoid for new code.

### b. Modern Date/Time API (`java.time` package, Java 8+)

**Common classes:**
- `LocalDate` — Date (year, month, day)
- `LocalTime` — Time (hours, minutes, seconds)
- `LocalDateTime` — Date and Time
- `DateTimeFormatter` — Formatting dates

**Example:**
```java
import java.time.*;

LocalDate today = LocalDate.now();
LocalTime now = LocalTime.now();
LocalDateTime dt = LocalDateTime.now();

System.out.println(today);         // e.g., 2025-06-08
System.out.println(now);           // e.g., 13:20:43.156
System.out.println(dt);            // e.g., 2025-06-08T13:20:43.156

// Formatting
import java.time.format.DateTimeFormatter;
DateTimeFormatter fmt = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm");
System.out.println(dt.format(fmt));  // 08-06-2025 13:20
```

---

## 🎯 Task Checklist

- [x] Use the `Math` class for calculations.
- [x] Manipulate arrays with methods from the `Arrays` class.
- [x] Build and modify strings using `StringBuffer` or `StringBuilder`.
- [x] Work with the date and time API to get and format current date/time.

---

**Awesome! Next, you'll begin planning your mini project.**