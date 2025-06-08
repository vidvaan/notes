# Day 8: Arrays

Welcome to Day 8! Today you’ll learn about **arrays** in Java: how to use 1D and 2D arrays, and how to perform basic array operations like traversal, insertion, and deletion.

---

## 1. What is an Array?

An **array** is a collection of elements of the same data type, stored in a contiguous memory location. Each element is accessed by its index (starting from 0).

---

## 2. 1D Arrays

### Declaration and Initialization

```java
int[] numbers = new int[5];               // Declaration (default values: 0)
numbers[0] = 10;                          // Assignment

int[] moreNumbers = {1, 2, 3, 4, 5};      // Declaration + initialization
```

### Traversal (Printing All Elements)

```java
for (int i = 0; i < moreNumbers.length; i++) {
    System.out.println(moreNumbers[i]);
}
// OR using enhanced for-loop:
for (int num : moreNumbers) {
    System.out.println(num);
}
```

---

## 3. 2D Arrays

### Declaration and Initialization

```java
int[][] matrix = new int[2][3]; // 2 rows, 3 columns

matrix[0][0] = 1;
matrix[0][1] = 2;
matrix[0][2] = 3;
matrix[1][0] = 4;
matrix[1][1] = 5;
matrix[1][2] = 6;

// Initialization with values
int[][] table = {
    {1, 2, 3},
    {4, 5, 6}
};
```

### Traversal (Printing All Elements)
```java
for (int i = 0; i < table.length; i++) {
    for (int j = 0; j < table[i].length; j++) {
        System.out.print(table[i][j] + " ");
    }
    System.out.println();
}
// OR using enhanced for-loop:
for (int[] row : table) {
    for (int val : row) {
        System.out.print(val + " ");
    }
    System.out.println();
}
```

---

## 4. Array Operations

### a. Traversal

Access each element one by one (see above).

### b. Insertion

Arrays have **fixed size**. To "insert", you set a value at a given index:

```java
moreNumbers[2] = 99; // Sets 3rd element to 99
```

For dynamic insertion, use `ArrayList` (covered later).

### c. Deletion

You can't shrink an array directly. To "delete" an element, set it to a default value (e.g., 0 for int):

```java
moreNumbers[1] = 0; // Sets 2nd element to 0
```

For actual resizing/removal, use `ArrayList`.

---

## 5. Example: Sum of Array Elements

```java
public class ArraySum {
    public static void main(String[] args) {
        int[] arr = {3, 5, 7, 9, 11};
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        System.out.println("Sum: " + sum);
    }
}
```

---

## 6. Example: Traversing a 2D Array

```java
public class MatrixPrint {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6}
        };
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

## 🎯 Task Checklist

- [x] Declare, initialize, and traverse a 1D array.
- [x] Declare, initialize, and traverse a 2D array.
- [x] Write a program to find the largest element in a 1D array.
- [x] Practice insertion and "deletion" (resetting value) in arrays.

---

**Great! Tomorrow you'll learn about Strings in Java.**