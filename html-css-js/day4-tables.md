# Day 4: Tables

Welcome to Day 4! Today, you'll learn how to create and structure tables in HTML. Tables are useful for displaying data in rows and columns, such as schedules, price lists, and more.

---

## 1. Basic Table Structure

The main tags used for tables are:

- `<table>`: Defines the table.
- `<tr>`: Table row.
- `<th>`: Table header cell (bold and centered by default).
- `<td>`: Table data cell.

**Example:**
```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Alice</td>
    <td>24</td>
  </tr>
  <tr>
    <td>Bob</td>
    <td>30</td>
  </tr>
</table>
```

---

## 2. Table Sections

- `<thead>`: Groups the header content.
- `<tbody>`: Groups the main body content.
- `<tfoot>`: Groups the footer content.

**Example with sections:**
```html
<table>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apple</td>
      <td>$1</td>
    </tr>
    <tr>
      <td>Banana</td>
      <td>$0.50</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>$1.50</td>
    </tr>
  </tfoot>
</table>
```

---

## 3. Additional Table Tips

- You can add as many rows (`<tr>`) and columns (`<th>`/`<td>`) as needed.
- Use CSS later for styling tables.
- For complex tables, use `<thead>`, `<tbody>`, and `<tfoot>` to improve readability and accessibility.

---

## 🎯 Task Checklist

- [x] Create a simple table using `<table>`, `<tr>`, `<th>`, and `<td>`.
- [x] Add table sections with `<thead>`, `<tbody>`, and `<tfoot>`.
- [x] Try displaying different types of data (e.g., contacts, schedules, products).

---

**Great job! You've learned how to organize data in tables. Tomorrow you'll explore forms in HTML.**