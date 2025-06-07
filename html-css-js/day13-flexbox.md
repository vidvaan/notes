# Day 13: Flexbox

Welcome to Day 13! Today, you'll learn about **Flexbox**—a modern CSS layout module that makes it easy to arrange items in rows, columns, and grids, and to align and distribute space among them.

---

## 1. What is Flexbox?

**Flexbox** (Flexible Box Layout) is a CSS3 layout model for efficiently aligning and distributing space among items in a container, even when their sizes are unknown or dynamic. It's perfect for building responsive navigation bars, card layouts, and more.

---

## 2. The Flex Container

To use Flexbox, set the container's `display` property to `flex` (or `inline-flex`).

```css
.flex-container {
  display: flex;
}
```

All direct children of this container become **flex items**.

---

## 3. Main Flexbox Properties

### a. `flex-direction`

Determines the direction of the main axis (how items are placed in the container).

- `row` (default): left to right
- `row-reverse`: right to left
- `column`: top to bottom
- `column-reverse`: bottom to top

```css
.flex-container {
  flex-direction: row;
}
```

### b. `justify-content`

Aligns items **along the main axis** (horizontal in row, vertical in column).

- `flex-start` (default): items start at the beginning
- `flex-end`: items end at the end
- `center`: items centered
- `space-between`: even spacing, no space at ends
- `space-around`: even space around each item
- `space-evenly`: equal space between and at ends

```css
.flex-container {
  justify-content: space-between;
}
```

### c. `align-items`

Aligns items **along the cross axis** (vertical in row, horizontal in column).

- `stretch` (default): stretches to fill container
- `flex-start`: align to start
- `flex-end`: align to end
- `center`: align to center
- `baseline`: align to text baseline

```css
.flex-container {
  align-items: center;
}
```

### d. `gap`

Sets the space between flex items (no need for margin hacks!).

```css
.flex-container {
  gap: 20px;
}
```

### e. `flex-wrap`

Controls whether items stay on one line or wrap onto multiple lines.

- `nowrap` (default): all items on one line
- `wrap`: items wrap onto multiple lines
- `wrap-reverse`: items wrap in reverse

```css
.flex-container {
  flex-wrap: wrap;
}
```

---

## 4. Example: Putting It All Together

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Flexbox Example</title>
    <style>
      .flex-container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
        gap: 20px;
        background: #f0f8ff;
        padding: 30px;
        border-radius: 10px;
      }
      .flex-item {
        background: #2196f3;
        color: #fff;
        padding: 30px 20px;
        font-size: 1.3em;
        text-align: center;
        border-radius: 8px;
        flex: 1 1 200px; /* Grow, shrink, base width */
        min-width: 120px;
      }
    </style>
  </head>
  <body>
    <div class="flex-container">
      <div class="flex-item">Item 1</div>
      <div class="flex-item">Item 2</div>
      <div class="flex-item">Item 3</div>
      <div class="flex-item">Item 4</div>
    </div>
  </body>
</html>
```

---

## 5. More Useful Flexbox Features

- **Align a single item**:  
  Use `align-self` on any flex item to override the container's `align-items`.
  ```css
  .flex-item.special {
    align-self: flex-end;
  }
  ```

- **Flexible item sizing**:  
  Use the `flex` shorthand (`flex-grow flex-shrink flex-basis`).
  ```css
  .flex-item {
    flex: 2 1 150px; /* grow 2x, shrink, base 150px */
  }
  ```

---

## 6. Best Practices

- Use Flexbox for one-dimensional layouts (rows OR columns).
- Use `gap` for spacing between items.
- Avoid using margin for spacing between flex items unless for special cases.
- Combine with media queries for responsive layouts.

---

## 🎯 Task Checklist

- [x] Make a flex container and add some flex items.
- [x] Change direction, alignment, and spacing with `flex-direction`, `justify-content`, `align-items`, and `gap`.
- [x] Experiment with wrapping (`flex-wrap`) and responsive layouts by resizing your browser.
- [x] Try aligning a single item with `align-self`.

---

**Awesome! You’ve unlocked the power of Flexbox. Next, you’ll learn about CSS Grid for even more advanced layouts!**