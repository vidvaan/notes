# Day 22: File Input/Output

Welcome to Day 22! Today, you'll learn how to read from and write to files in Java using core classes like `File`, `FileReader`, `FileWriter`, and `BufferedReader`. Understanding File I/O is essential for building real-world applications that work with data.

---

## 1. The `File` Class

- Represents file and directory pathnames.
- Used to check file properties, create/delete files, and list directories.

**Example:**
```java
import java.io.File;

public class FileExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        System.out.println("Exists? " + file.exists());
        System.out.println("Absolute Path: " + file.getAbsolutePath());
    }
}
```

---

## 2. Writing to Files

### a. Using `FileWriter`

- Writes character data to a file.
- By default, overwrites the file; use `FileWriter(filename, true)` for appending.

**Example:**
```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteFileExample {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("output.txt");
            fw.write("Hello, Java File I/O!\n");
            fw.write("Second line.");
            fw.close();
            System.out.println("File written successfully.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 3. Reading from Files

### a. Using `FileReader` and `BufferedReader`

- `FileReader` reads character data.
- `BufferedReader` makes reading efficient and allows reading lines.

**Example:**
```java
import java.io.FileReader;
import java.io.BufferedReader;
import java.io.IOException;

public class ReadFileExample {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("output.txt");
            BufferedReader br = new BufferedReader(fr);
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
            fr.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 4. Appending to Files

**Example:**
```java
FileWriter fw = new FileWriter("output.txt", true); // true = append mode
fw.write("\nAppended line.");
fw.close();
```

---

## 5. Other Useful File Operations

- **Check if a file exists:** `file.exists()`
- **Delete a file:** `file.delete()`
- **Get file length:** `file.length()`
- **List files in a directory:**
    ```java
    File dir = new File(".");
    for (String fname : dir.list()) {
        System.out.println(fname);
    }
    ```

---

## 6. Note on Exception Handling

- Most File I/O classes throw `IOException`.
- Always handle with `try-catch` or declare `throws IOException`.

---

## 7. Complete Example: Write and Read

```java
import java.io.*;

public class FileIODemo {
    public static void main(String[] args) {
        // Writing
        try (FileWriter fw = new FileWriter("demo.txt")) {
            fw.write("This is a demo file.\nWelcome to Java File I/O!");
        } catch (IOException e) {
            e.printStackTrace();
        }

        // Reading
        try (BufferedReader br = new BufferedReader(new FileReader("demo.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🎯 Task Checklist

- [x] Check if a file exists using the `File` class.
- [x] Write text to a file using `FileWriter`.
- [x] Read text from a file using `FileReader` and `BufferedReader`.
- [x] Try appending data to an existing file.
- [x] Handle exceptions properly.

---

**Nice! Tomorrow you'll learn the basics of multithreading in Java.**