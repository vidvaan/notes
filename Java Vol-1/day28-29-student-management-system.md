# Day 28-29: Mini Project Implementation  
**Project:** Student Management System

---

## Project Overview

This simple **Student Management System** is a console-based Java application that allows you to add, view, search, update, and delete student records. It uses OOP, Collections (`ArrayList`), File I/O, and basic exception handling.

---

## Features

- Add a new student
- View all students
- Search for a student by ID
- Update student details
- Delete a student
- Save/load data from a text file

---

## Code Implementation

### 1. Student.java

```java
import java.io.Serializable;

public class Student implements Serializable {
    private int id;
    private String name;
    private int age;
    private double grade;

    public Student(int id, String name, int age, double grade) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.grade = grade;
    }
    // Getters and setters
    public int getId() { return id; }
    public String getName() { return name; }
    public int getAge() { return age; }
    public double getGrade() { return grade; }

    public void setName(String name) { this.name = name; }
    public void setAge(int age) { this.age = age; }
    public void setGrade(double grade) { this.grade = grade; }

    @Override
    public String toString() {
        return id + "," + name + "," + age + "," + grade;
    }

    public static Student fromString(String line) {
        String[] parts = line.split(",");
        if (parts.length != 4) return null;
        try {
            int id = Integer.parseInt(parts[0]);
            String name = parts[1];
            int age = Integer.parseInt(parts[2]);
            double grade = Double.parseDouble(parts[3]);
            return new Student(id, name, age, grade);
        } catch (Exception e) {
            return null;
        }
    }
}
```

---

### 2. StudentManager.java

```java
import java.util.*;
import java.io.*;

public class StudentManager {
    private ArrayList<Student> students = new ArrayList<>();
    private final String filename = "students.txt";

    // Load students from file
    public void loadFromFile() {
        students.clear();
        try (BufferedReader br = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = br.readLine()) != null) {
                Student s = Student.fromString(line);
                if (s != null) students.add(s);
            }
        } catch (IOException e) {
            // File may not exist on first run; that's fine.
        }
    }

    // Save students to file
    public void saveToFile() {
        try (PrintWriter pw = new PrintWriter(new FileWriter(filename))) {
            for (Student s : students) {
                pw.println(s.toString());
            }
        } catch (IOException e) {
            System.out.println("Error writing to file.");
        }
    }

    public boolean addStudent(Student s) {
        for (Student st : students) {
            if (st.getId() == s.getId()) {
                return false; // Duplicate ID
            }
        }
        students.add(s);
        return true;
    }

    public List<Student> getAllStudents() {
        return students;
    }

    public Student searchById(int id) {
        for (Student s : students) {
            if (s.getId() == id) return s;
        }
        return null;
    }

    public boolean removeStudent(int id) {
        Iterator<Student> it = students.iterator();
        while (it.hasNext()) {
            if (it.next().getId() == id) {
                it.remove();
                return true;
            }
        }
        return false;
    }
}
```

---

### 3. Main.java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        StudentManager manager = new StudentManager();
        manager.loadFromFile();
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n--- Student Management System ---");
            System.out.println("1. Add Student");
            System.out.println("2. View All Students");
            System.out.println("3. Search Student by ID");
            System.out.println("4. Update Student");
            System.out.println("5. Delete Student");
            System.out.println("6. Save & Exit");
            System.out.print("Enter choice: ");
            int choice;
            try {
                choice = Integer.parseInt(sc.nextLine());
            } catch (Exception e) {
                System.out.println("Invalid input!");
                continue;
            }

            switch (choice) {
                case 1:
                    System.out.print("Enter ID: ");
                    int id = Integer.parseInt(sc.nextLine());
                    System.out.print("Enter Name: ");
                    String name = sc.nextLine();
                    System.out.print("Enter Age: ");
                    int age = Integer.parseInt(sc.nextLine());
                    System.out.print("Enter Grade: ");
                    double grade = Double.parseDouble(sc.nextLine());
                    Student s = new Student(id, name, age, grade);
                    if (manager.addStudent(s))
                        System.out.println("Student added!");
                    else
                        System.out.println("Student with this ID already exists!");
                    break;
                case 2:
                    System.out.println("--- All Students ---");
                    for (Student st : manager.getAllStudents()) {
                        System.out.println("ID: " + st.getId() +
                                           ", Name: " + st.getName() +
                                           ", Age: " + st.getAge() +
                                           ", Grade: " + st.getGrade());
                    }
                    break;
                case 3:
                    System.out.print("Enter ID to search: ");
                    int sid = Integer.parseInt(sc.nextLine());
                    Student found = manager.searchById(sid);
                    if (found != null)
                        System.out.println("Found: " + found);
                    else
                        System.out.println("Student not found.");
                    break;
                case 4:
                    System.out.print("Enter ID to update: ");
                    int uid = Integer.parseInt(sc.nextLine());
                    Student toUpdate = manager.searchById(uid);
                    if (toUpdate != null) {
                        System.out.print("New Name (" + toUpdate.getName() + "): ");
                        String newName = sc.nextLine();
                        if (!newName.isEmpty()) toUpdate.setName(newName);

                        System.out.print("New Age (" + toUpdate.getAge() + "): ");
                        String newAge = sc.nextLine();
                        if (!newAge.isEmpty()) toUpdate.setAge(Integer.parseInt(newAge));

                        System.out.print("New Grade (" + toUpdate.getGrade() + "): ");
                        String newGrade = sc.nextLine();
                        if (!newGrade.isEmpty()) toUpdate.setGrade(Double.parseDouble(newGrade));

                        System.out.println("Student updated!");
                    } else {
                        System.out.println("Student not found.");
                    }
                    break;
                case 5:
                    System.out.print("Enter ID to delete: ");
                    int did = Integer.parseInt(sc.nextLine());
                    if (manager.removeStudent(did))
                        System.out.println("Student deleted.");
                    else
                        System.out.println("Student not found.");
                    break;
                case 6:
                    manager.saveToFile();
                    System.out.println("Data saved. Exiting...");
                    sc.close();
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

## 4. How to Run

1. Save the three classes (`Student.java`, `StudentManager.java`, `Main.java`) in the same directory.
2. Compile:
    ```
    javac Student.java StudentManager.java Main.java
    ```
3. Run:
    ```
    java Main
    ```
4. Data will be saved to `students.txt` in the same directory.

---

## 5. Concepts Used

- **OOP:** Encapsulation (Student class), separation of concerns
- **Collections:** `ArrayList<Student>`
- **File I/O:** Reading/writing student data from/to file
- **Exception Handling:** For input and file operations

---

## 🎯 Task Checklist

- [x] Implement core CRUD features for students
- [x] Use OOP and encapsulation
- [x] Use ArrayList for storage
- [x] Use File I/O for persistence
- [x] Handle invalid input and duplicate IDs

---

**Well done! On Day 30, you’ll review your project and plan your next steps.**