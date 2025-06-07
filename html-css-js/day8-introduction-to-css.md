# Day 8: Introduction to CSS

Welcome to Day 8! Today, you'll start your journey into CSS—the language that brings style and life to your web pages. This lesson covers what CSS is, how to include it in your HTML, and the basics of selectors, properties, and values.

---

## 1. What is CSS?

**CSS (Cascading Style Sheets)** is a stylesheet language used to describe the presentation (look and formatting) of HTML documents.  
While HTML structures your content, CSS controls how it appears—colors, fonts, layout, spacing, and much more.

### Why use CSS?
- **Separation of Concerns:** Keeps your content (HTML) separate from your design (CSS).
- **Consistency:** Apply the same styles across multiple pages easily.
- **Maintainability:** Change the look of your website by editing one file.
- **Responsiveness:** Adapt layouts to different devices and screen sizes.

---

## 2. Ways to Add CSS

There are three main ways to add CSS to your HTML:

### a. Inline CSS

Apply styles directly to HTML elements using the `style` attribute.

**Example:**
```html
<p style="color: blue; font-weight: bold;">This is a blue, bold paragraph.</p>
```

**When to use?**  
For quick, one-off changes or testing. Not recommended for large projects.

---

### b. Internal CSS (Embedded)

Place your CSS rules inside a `<style>` tag within the `<head>` section of your HTML file.

**Example:**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Internal CSS Example</title>
    <style>
      h1 {
        color: darkgreen;
      }
      p {
        font-size: 18px;
      }
    </style>
  </head>
  <body>
    <h1>Welcome!</h1>
    <p>This is styled with internal CSS.</p>
  </body>
</html>
```

**When to use?**  
For single-page websites or when styles are only needed on one page.

---

### c. External CSS

Write your CSS in a separate `.css` file and link it to your HTML using the `<link>` tag.

**Example (HTML):**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>External CSS Example</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <p>This is styled with external CSS.</p>
  </body>
</html>
```

**Example (`styles.css`):**
```css
h1 {
  color: purple;
}
p {
  font-family: Arial, sans-serif;
}
```

**When to use?**  
For all multi-page or production websites. This is the recommended approach.

---

## 3. CSS Syntax: Selectors, Properties, Values

### Basic Structure

```css
selector {
  property: value;
  property2: value2;
}
```

### a. Selectors

Selectors specify which HTML elements the styles apply to.

**Types of Selectors:**
- **Element selector:** Targets all elements of a type  
  ```css
  p { color: red; }
  ```
- **Class selector:** Targets elements with a specific class  
  ```css
  .highlight { background: yellow; }
  ```
  ```html
  <p class="highlight">Highlighted text.</p>
  ```
- **ID selector:** Targets a unique element with an id  
  ```css
  #main-title { font-size: 32px; }
  ```
  ```html
  <h1 id="main-title">Main Title</h1>
  ```
- **Grouping selectors:** Apply same styles to multiple elements  
  ```css
  h1, h2, h3 { font-family: Verdana; }
  ```
- **Descendant selector:** Targets elements inside other elements  
  ```css
  nav a { color: green; }
  ```

### b. Properties

Properties are what you want to change (color, font-size, background, margin, etc.).

**Examples:**  
- `color`
- `background-color`
- `font-size`
- `margin`
- `padding`
- `border`

### c. Values

Values specify the settings for each property.

**Examples:**  
- `color: blue;`
- `font-size: 20px;`
- `background-color: #f1f1f1;`
- `margin: 10px 20px;`

---

## 4. Example: Putting It All Together

**HTML:**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>CSS Demo</title>
    <style>
      body {
        background-color: #f9f9f9;
        font-family: Arial, sans-serif;
      }
      h1 {
        color: #2e8b57;
        text-align: center;
      }
      .important {
        color: red;
        font-weight: bold;
      }
      #footer {
        margin-top: 40px;
        text-align: center;
        font-size: 14px;
        color: #888;
      }
    </style>
  </head>
  <body>
    <h1>Hello, CSS!</h1>
    <p>This is a normal paragraph.</p>
    <p class="important">This paragraph is very important!</p>
    <div id="footer">Made with ❤️ using CSS</div>
  </body>
</html>
```

---

## 5. Best Practices

- Use **external CSS** for all but the smallest projects.
- Use **meaningful class and id names** (avoid names like `red-text` or `big-font`).
- Keep your CSS organized and well-commented.
- Avoid inline CSS for maintainability.

---

## 🎯 Task Checklist

- [x] Try all three ways to add CSS (inline, internal, external).
- [x] Create a simple external CSS file and link it to an HTML file.
- [x] Practice using element, class, and id selectors.
- [x] Change text color, font, and background of various elements.

---

**Awesome! You’ve taken your first step into the world of CSS. Tomorrow you’ll dive deeper into colors and typography.**