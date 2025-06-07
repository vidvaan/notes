# Day 28: Responsive Design Basics

Welcome to Day 28! Today you'll learn the essentials of **responsive web design**—making websites look good on all devices, from phones to desktops. You'll focus on **media queries** and the **mobile-first approach**.

---

## 1. What is Responsive Design?

Responsive design means your web page automatically adapts its layout and styling to fit different screen sizes and devices.

---

## 2. The Viewport Meta Tag

Always include this tag in your HTML `<head>` for proper scaling on mobile devices:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 3. Media Queries

**Media queries** are special CSS rules that apply styles only if certain conditions are met—like screen width, height, orientation, etc.

**Syntax:**
```css
@media (condition) {
  /* CSS here only applies if condition is true */
}
```

### Example: Basic Media Query

```css
body {
  background: #fff;
}

@media (max-width: 600px) {
  body {
    background: #e3f2fd;
  }
}
```
The background will be light blue on screens 600px wide or less, white otherwise.

---

## 4. Mobile-First Layout

The **mobile-first** approach means:
- Write your default CSS for small screens (mobile).
- Use media queries to adjust for larger screens (tablet, desktop).

**Example:**
```css
/* Mobile styles (default) */
.container {
  width: 100%;
  padding: 12px;
}

/* Tablet and up */
@media (min-width: 600px) {
  .container {
    width: 80%;
    margin: 0 auto;
  }
}

/* Desktop and up */
@media (min-width: 900px) {
  .container {
    width: 60%;
  }
}
```

---

## 5. Responsive Example: Card Layout

```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Cards Example</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        margin: 0;
        background: #f8fafc;
      }
      .container {
        padding: 16px;
        display: flex;
        flex-direction: column;
        gap: 16px;
      }
      .card {
        background: #fff;
        border-radius: 8px;
        padding: 20px;
        box-shadow: 0 2px 8px #bdbdbd22;
      }
      /* Tablet: stack side by side */
      @media (min-width: 600px) {
        .container {
          flex-direction: row;
        }
        .card {
          flex: 1;
        }
      }
      /* Desktop: larger max width */
      @media (min-width: 900px) {
        .container {
          max-width: 900px;
          margin: 24px auto;
        }
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="card">Card 1: Mobile first!</div>
      <div class="card">Card 2: Try resizing the window.</div>
      <div class="card">Card 3: Responsive magic ✨</div>
    </div>
  </body>
</html>
```

---

## 6. Best Practices

- **Start with mobile styles first**, then add media queries for larger screens.
- Use relative units (%, em, rem, vw, vh) for widths, margins, and padding.
- Test your layout on different devices or using browser dev tools ("Toggle Device Toolbar").
- Avoid fixed pixel widths for main containers.

---

## 🎯 Task Checklist

- [x] Add a viewport meta tag to your HTML.
- [x] Use media queries to adjust layout for different screen sizes.
- [x] Build a simple mobile-first, responsive layout (e.g., cards, navbar).

---

**Well done! Now your websites will look great on phones, tablets, and desktops.**