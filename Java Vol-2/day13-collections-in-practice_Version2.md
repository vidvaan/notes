# Day 13: Collections in Practice

Today you'll apply your understanding of Java Collections by designing practical data structures and building a simple mini-project. You'll see how nested collections work and implement a basic **Student Directory** using a `Student` object.

---

## 1. Designing Data Structures with Collections

Collections allow you to organize and manage data efficiently:
- **List**: Ordered collection, allows duplicates.
- **Set**: Unordered, unique elements.
- **Map**: Key-value pairs (e.g., `Map<Integer, Student>`).

### Example: Student Directory

Suppose you want to manage students by their class or section. You can use:
- `Map<String, List<Student>>` — Key: class/section, Value: list of students in that section.

---

## 2. Nested Collections Example

```java
import java.util.*;

class Student {
    private int id;
    private String name;
    private int age;
    public Student(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }
    public String toString() {
        return id + " - " + name + " (" + age + ")";
    }
    public int getId() { return id; }
    public String getName() { return name; }
    public int getAge() { return age; }
}

public class StudentDirectory {
    public static void main(String[] args) {
        Map<String, List<Student>> directory = new HashMap<>();

        // Adding students
        directory.put("A", new ArrayList<>());
        directory.put("B", new ArrayList<>());

        directory.get("A").add(new Student(1, "Alice", 20));
        directory.get("A").add(new Student(2, "Arun", 21));
        directory.get("B").add(new Student(3, "Bob", 22));

        // Print all students in section A
        System.out.println("Section A: " + directory.get("A"));

        // Print all students in the directory
        for (String section : directory.keySet()) {
            System.out.println("Section " + section + ": " + directory.get(section));
        }
    }
}
```

---

## 3. Mini-Project: Simple Student Directory

### Requirements

- Add a student to a section
- Remove a student by ID
- List all students in a section
- List all students in all sections

### Sample Code

```java
import java.util.*;

class Student {
    private int id;
    private String name;
    private int age;
    public Student(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }
    public int getId() { return id; }
    public String getName() { return name; }
    public int getAge() { return age; }
    public String toString() { return id + ": " + name + " (" + age + ")"; }
}

public class StudentDirectoryApp {
    private static Map<String, List<Student>> directory = new HashMap<>();
    private static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        while (true) {
            System.out.println("\n-- Student Directory --");
            System.out.println("1. Add student");
            System.out.println("2. Remove student by ID");
            System.out.println("3. List students in section");
            System.out.println("4. List all students");
            System.out.println("5. Exit");
            System.out.print("Enter choice: ");
            int choice = Integer.parseInt(sc.nextLine());
            switch (choice) {
                case 1: addStudent(); break;
                case 2: removeStudent(); break;
                case 3: listSection(); break;
                case 4: listAll(); break;
                case 5: return;
                default: System.out.println("Invalid choice.");
            }
        }
    }

    private static void addStudent() {
        System.out.print("Enter section: ");
        String section = sc.nextLine();
        System.out.print("Enter student ID: ");
        int id = Integer.parseInt(sc.nextLine());
        System.out.print("Enter name: ");
        String name = sc.nextLine();
        System.out.print("Enter age: ");
        int age = Integer.parseInt(sc.nextLine());
        Student s = new Student(id, name, age);
        directory.putIfAbsent(section, new ArrayList<>());
        directory.get(section).add(s);
        System.out.println("Student added.");
    }

    private static void removeStudent() {
        System.out.print("Enter section: ");
        String section = sc.nextLine();
        System.out.print("Enter student ID to remove: ");
        int id = Integer.parseInt(sc.nextLine());
        List<Student> students = directory.get(section);
        if (students != null) {
            students.removeIf(stu -> stu.getId() == id);
            System.out.println("If present, student removed.");
        } else {
            System.out.println("Section not found.");
        }
    }

    private static void listSection() {
        System.out.print("Enter section: ");
        String section = sc.nextLine();
        List<Student> students = directory.get(section);
        if (students != null) {
            System.out.println("Students in section " + section + ":");
            for (Student s : students)
                System.out.println(s);
        } else {
            System.out.println("Section not found.");
        }
    }

    private static void listAll() {
        if (directory.isEmpty()) {
            System.out.println("No students.");
            return;
        }
        for (String section : directory.keySet()) {
            System.out.println("Section " + section + ":");
            for (Student s : directory.get(section))
                System.out.println("  " + s);
        }
    }
}
```

---

## 4. Key Points

- **Nested collections** (e.g., `Map<String, List<Student>>`) are powerful for modeling real-world data.
- Practice CRUD (Create, Read, Update, Delete) operations using collections.
- Use OOP to encapsulate data (Student class).

---

## 🎯 Task Checklist

- [x] Design a nested collection structure for a real-world problem.
- [x] Implement a `Student` object and basic operations.
- [x] Practice CRUD operations on collections.
- [x] Try extending the mini-project: search by name, update student info, persist data, etc.

---

**Great work! Next, you'll start exploring Java 8 features.**