# Day 20: JDBC Advanced and Best Practices

Today you'll learn advanced JDBC features that help you write robust, efficient, and secure database code.

---

## 1. CallableStatement (Calling Stored Procedures)

- **CallableStatement** is used to execute stored procedures in the database.

**Example:**
Suppose you have a stored procedure:
```sql
CREATE PROCEDURE getStudentCount(OUT count INT)
BEGIN
    SELECT COUNT(*) INTO count FROM students;
END
```

**Java code to call it:**
```java
CallableStatement cs = conn.prepareCall("{call getStudentCount(?)}");
cs.registerOutParameter(1, java.sql.Types.INTEGER);
cs.execute();
int count = cs.getInt(1);
System.out.println("Student count: " + count);
cs.close();
```
- Use `setXXX(index, value)` to pass IN parameters, and `registerOutParameter` for OUT parameters.

---

## 2. Transactions and Batch Processing

### a. Transactions

- A **transaction** is a group of SQL statements that are executed as a single unit. If one fails, all are rolled back.
- Managed using `conn.setAutoCommit(false)`, `conn.commit()`, and `conn.rollback()`.

**Example:**
```java
conn.setAutoCommit(false);
try {
    stmt.executeUpdate("UPDATE students SET age = age + 1 WHERE id = 1");
    stmt.executeUpdate("UPDATE students SET age = age + 1 WHERE id = 2");
    conn.commit(); // Both succeed
} catch (SQLException ex) {
    conn.rollback(); // If any fails, all are rolled back
}
```

### b. Batch Processing

- Batch processing lets you group multiple SQL statements to send to the database in one go, improving performance.

**Example:**
```java
PreparedStatement ps = conn.prepareStatement("INSERT INTO students (name, age) VALUES (?, ?)");
ps.setString(1, "Alice");
ps.setInt(2, 22);
ps.addBatch();

ps.setString(1, "Bob");
ps.setInt(2, 23);
ps.addBatch();

int[] results = ps.executeBatch();
ps.close();
```
- Use `addBatch()` for each statement, then `executeBatch()`.

---

## 3. Exception Handling in JDBC

- Always catch `SQLException` (and optionally, general `Exception`).
- Log or print exception details: `ex.getMessage()`, `ex.getErrorCode()`, `ex.getSQLState()`.
- Use finally or try-with-resources to ensure resources are closed.

**Example:**
```java
try {
    // JDBC code
} catch (SQLException ex) {
    ex.printStackTrace();
    // or log error
}
```

---

## 4. Closing Resources and Try-with-Resources

- JDBC objects (`Connection`, `Statement`, `ResultSet`) must be closed to free resources.
- Java 7+ enables **try-with-resources** for auto-closing.

**Example:**
```java
try (
    Connection conn = DriverManager.getConnection("jdbc:sqlite:test.db");
    Statement stmt = conn.createStatement();
    ResultSet rs = stmt.executeQuery("SELECT * FROM students");
) {
    while (rs.next()) {
        System.out.println(rs.getString("name"));
    }
} catch (SQLException ex) {
    ex.printStackTrace();
}
// Resources are auto-closed
```
- This pattern reduces leaks and is **best practice** for JDBC.

---

## 5. Summary Table

| Feature             | How/Why to Use                                               |
|---------------------|-------------------------------------------------------------|
| CallableStatement   | Call stored procedures (IN/OUT params, business logic)      |
| Transactions        | Ensure multiple operations succeed or fail as a unit        |
| Batch Processing    | Speed up bulk inserts/updates                               |
| Exception Handling  | Catch/log database errors, avoid crashes                    |
| Try-with-Resources  | Automatically close JDBC resources, prevent leaks           |

---

## 🎯 Task Checklist

- [x] Use CallableStatement to call a stored procedure.
- [x] Practice transactions (commit/rollback).
- [x] Batch-insert or update multiple records.
- [x] Always close resources, preferably with try-with-resources.

---

**Congratulations! You’ve completed the 20-day Java Advanced Plan!**