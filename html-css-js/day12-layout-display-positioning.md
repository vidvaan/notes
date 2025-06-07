# Day 12: Layout: Display & Positioning

Welcome to Day 12! Today, you’ll learn how to control the layout of elements using CSS display types, positioning, stacking order, and floating. These tools are essential for creating flexible, responsive web designs.

---

## 1. The `display` Property

The `display` property determines how an element is rendered in the document flow.

### a. Block Elements

- Take up the full width available.
- Start on a new line.
- Examples: `<div>`, `<h1>`, `<p>`, `<section>`

```css
div {
  display: block;
}
```

### b. Inline Elements

- Only take up as much width as needed.
- Do not start on a new line.
- Examples: `<span>`, `<a>`, `<strong>`, `<img>`

```css
span {
  display: inline;
}
```

### c. Inline-Block Elements

- Behave like inline elements but can have width, height, margin, and padding.
- Useful for laying out items horizontally while retaining block-level box control.

```css
.button {
  display: inline-block;
  padding: 10px 20px;
  background: #2196f3;
  color: white;
  border-radius: 5px;
}
```

### d. None

- Completely removes the element from the layout (it won’t be visible or take up any space).

```css
.hidden {
  display: none;
}
```

---

## 2. The `position` Property

The `position` property controls how an element is positioned in the document.

### a. static (default)

- Element is positioned according to the normal flow of the page.
- Top, right, bottom, left, and z-index have no effect.

```css
.header {
  position: static;
}
```

### b. relative

- Element is positioned relative to its normal position.
- You can use `top`, `right`, `bottom`, and `left` to offset it.

```css
.box {
  position: relative;
  top: 20px;   /* moves down 20px */
  left: 10px;  /* moves right 10px */
}
```

### c. absolute

- Element is removed from the normal flow and positioned relative to its nearest positioned ancestor (not static).
- If no ancestor is positioned, it’s relative to `<html>` (the page).

```css
.child {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

### d. fixed

- Element is positioned relative to the browser window.
- Stays in the same place even when scrolling.

```css
.menu {
  position: fixed;
  top: 0;
  right: 0;
}
```

### e. sticky

- Element toggles between relative and fixed, based on the user's scroll position.
- Sticks to the top when the scroll reaches its position.

```css
.sticky-header {
  position: sticky;
  top: 0;
  background: #fff;
}
```

---

## 3. The `z-index` Property

The `z-index` property controls the stacking order of absolutely, fixed, or relatively positioned elements.

- Higher `z-index` = appears on top.
- Only works on positioned elements.

```css
.box1 {
  position: absolute;
  z-index: 1;
}
.box2 {
  position: absolute;
  z-index: 2; /* appears above .box1 */
}
```

---

## 4. The `float` and `clear` Properties

### a. float

- Moves an element to the left or right, allowing text and inline elements to wrap around it.

```css
img {
  float: left;
  margin-right: 16px;
}
.sidebar {
  float: right;
}
```

### b. clear

- Prevents elements from wrapping around floated elements.

```css
.clearfix {
  clear: both; /* can be left, right, or both */
}
```

### c. Clearing Floats (Modern Method)

Use a clearfix hack to contain floated children:

```css
.container::after {
  content: "";
  display: table;
  clear: both;
}
```

---

## 5. Example: Display, Positioning, and Float

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Display & Positioning Example</title>
    <style>
      .block {
        display: block;
        background: #f1c40f;
        margin-bottom: 10px;
        padding: 10px;
      }
      .inline {
        display: inline;
        background: #e67e22;
        padding: 5px;
      }
      .inline-block {
        display: inline-block;
        background: #2ecc71;
        padding: 10px 20px;
        margin: 5px 0;
      }
      .relative-box {
        position: relative;
        top: 10px;
        left: 10px;
        background: #3498db;
        color: #fff;
        padding: 10px;
      }
      .absolute-box {
        position: absolute;
        top: 50px;
        left: 50px;
        background: #9b59b6;
        color: #fff;
        padding: 10px;
      }
      .fixed-box {
        position: fixed;
        bottom: 10px;
        right: 10px;
        background: #e74c3c;
        color: #fff;
        padding: 10px;
      }
      .sticky-box {
        position: sticky;
        top: 0;
        background: #95a5a6;
        padding: 10px;
      }
      .float-left {
        float: left;
        background: #8e44ad;
        color: #fff;
        width: 120px;
        margin-right: 12px;
        padding: 10px;
      }
      .float-right {
        float: right;
        background: #16a085;
        color: #fff;
        width: 120px;
        margin-left: 12px;
        padding: 10px;
      }
      .clearfix::after {
        content: "";
        display: table;
        clear: both;
      }
    </style>
  </head>
  <body>
    <div class="block">I am block</div>
    <span class="inline">I am inline</span>
    <span class="inline-block">I am inline-block</span>

    <div class="relative-box">Relative Box (offset 10px down and right)</div>
    <div style="position: relative; height: 120px; background: #ecf0f1; margin: 30px 0;">
      <div class="absolute-box">Absolute Box (inside relative parent)</div>
    </div>
    <div class="fixed-box">Fixed Box (bottom right corner)</div>
    <div class="sticky-box">Sticky Box (sticks to top on scroll)</div>

    <div class="clearfix" style="margin-top:40px;">
      <div class="float-left">Float Left</div>
      <div class="float-right">Float Right</div>
      <p>
        This paragraph will wrap around the floated boxes. Use clearfix to ensure the container grows to fit.
      </p>
    </div>
  </body>
</html>
```

---

## 6. Best Practices

- Avoid using `float` for page layouts (use Flexbox/Grid instead), but it’s fine for simple text wrapping.
- Only use `z-index` on positioned elements (`position` not static).
- Use `inline-block` for horizontal layouts where you need sizing/margin control.
- Use `position: sticky` for sticky headers or sidebars.
- Use `display: none` to hide elements completely.

---

## 🎯 Task Checklist

- [x] Practice using block, inline, and inline-block elements.
- [x] Experiment with all five `position` values.
- [x] Layer elements with `z-index`.
- [x] Float elements left and right, and clear floats.
- [x] Try sticky and fixed positioning.

---

**Great work! Next, you'll learn modern layout techniques with Flexbox and CSS Grid!**