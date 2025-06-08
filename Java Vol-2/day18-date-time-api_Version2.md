# Day 18: Date and Time API (java.time)

Java 8 introduced the **java.time** package, a modern, powerful, and thread-safe date and time API that replaces the outdated `Date` and `Calendar` classes. Today you'll learn to work with dates, times, and intervals in a much more intuitive way.

---

## 1. LocalDate, LocalTime, LocalDateTime

### a. LocalDate

- Represents a date (year, month, day) without time or timezone.
- **Example:**

```java
import java.time.LocalDate;

LocalDate today = LocalDate.now();
LocalDate birthday = LocalDate.of(1995, 5, 23);

System.out.println(today);        // e.g. 2025-06-08
System.out.println(birthday);     // 1995-05-23

// Add/subtract days/months/years
LocalDate nextWeek = today.plusWeeks(1);
LocalDate lastMonth = today.minusMonths(1);
System.out.println(nextWeek);     // 2025-06-15
```

---

### b. LocalTime

- Represents a time (hour, minute, second, nanosecond) without date or timezone.
- **Example:**

```java
import java.time.LocalTime;

LocalTime now = LocalTime.now();
LocalTime bedtime = LocalTime.of(23, 0);

System.out.println(now);         // e.g. 11:52:01.123
System.out.println(bedtime);     // 23:00
```

---

### c. LocalDateTime

- Combines date and time (no timezone).
- **Example:**

```java
import java.time.LocalDateTime;

LocalDateTime now = LocalDateTime.now();
LocalDateTime meeting = LocalDateTime.of(2025, 6, 8, 15, 30);

System.out.println(now);         // 2025-06-08T11:52:01.123
System.out.println(meeting);     // 2025-06-08T15:30
```

---

## 2. DateTimeFormatter

- Used to format and parse date/time objects.

**Example: Custom Formatting**

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

LocalDateTime now = LocalDateTime.now();
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");

String formatted = now.format(formatter);
System.out.println(formatted);   // e.g. 08/06/2025 11:52:01
```

**Example: Parsing**

```java
String dateStr = "23/05/1995 08:30:00";
LocalDateTime dt = LocalDateTime.parse(dateStr, formatter);
System.out.println(dt);   // 1995-05-23T08:30
```

---

## 3. Duration and Period

- **Duration:** Measures time in seconds/nanos (for time-based amounts).
- **Period:** Measures time in years/months/days (for date-based amounts).

**Duration Example:**

```java
import java.time.Duration;
import java.time.LocalTime;

LocalTime start = LocalTime.of(9, 0);
LocalTime end = LocalTime.of(11, 30);

Duration duration = Duration.between(start, end);
System.out.println(duration.toHours());          // 2
System.out.println(duration.toMinutes());        // 150
```

**Period Example:**

```java
import java.time.Period;
import java.time.LocalDate;

LocalDate today = LocalDate.now();
LocalDate exam = LocalDate.of(2025, 12, 25);

Period period = Period.between(today, exam);
System.out.println(period.getMonths());          // Months between today and exam date
System.out.println(period.getDays());            // Days (excluding months and years)
System.out.println(period);                      // e.g. P6M17D (6 months, 17 days)
```

---

## 4. Key Points

- `LocalDate`, `LocalTime`, and `LocalDateTime` are immutable and thread-safe.
- Use `DateTimeFormatter` for custom formats.
- Use `Duration` for time differences, `Period` for date differences.
- There are also classes for time-zones (`ZonedDateTime`) and instants (`Instant`) for advanced use.

---

## 🎯 Task Checklist

- [x] Practice creating and manipulating LocalDate, LocalTime, LocalDateTime.
- [x] Format and parse dates using DateTimeFormatter.
- [x] Calculate intervals with Duration and Period.
- [x] Try using these in a mini-project (like a scheduler or countdown timer).

---

**Next: JDBC—learn to connect Java applications to databases!**