# Day 11: Backgrounds & Borders

Welcome to Day 11! Today, you'll learn how to make your web pages visually appealing using CSS backgrounds and borders. You'll explore background colors, images, gradients, border styles, rounded corners, and box shadows.

---

## 1. Backgrounds

CSS gives you the power to style backgrounds in many creative ways.

---

### a. Background Color

Set the background color of any element.

```css
body {
  background-color: #f5f6fa;
}

.highlight {
  background-color: yellow;
}
```
You can use color names, hex codes, rgb/rgba, or hsl/hsla.

---

### b. Background Images

Add an image as a background for any element.

```css
body {
  background-image: url('background.jpg');
}
```

#### Additional properties:

- `background-repeat`: Controls if/how the image repeats  
  - `repeat` (default), `no-repeat`, `repeat-x`, `repeat-y`
- `background-position`: Sets image position (e.g., `center`, `top right`, `50% 50%`)
- `background-size`: Controls image sizing  
  - `cover` (fills the area, cropping if needed), `contain` (fits inside area), or specific sizes
- `background-attachment`: Fixed or scrolls with page (`scroll`, `fixed`)

**Example:**
```css
.header {
  background-image: url('header-bg.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}
```

---

### c. Background Gradients

CSS gradients let you blend colors smoothly without images.

- **Linear Gradients:**  
  ```css
  .gradient-box {
    background: linear-gradient(90deg, #ff9800, #f44336);
  }
  ```
  - `90deg` sets the direction (90 degrees = left to right).

- **Radial Gradients:**  
  ```css
  .radial {
    background: radial-gradient(circle, #2196f3, #e1bee7);
  }
  ```

- **Repeating Gradients (advanced):**
  ```css
  .repeat-gradient {
    background: repeating-linear-gradient(45deg, #f06, #f06 10px, #ffeb3b 10px, #ffeb3b 20px);
  }
  ```

---

## 2. Borders

Borders define the edge of an element and can be styled in many ways.

---

### a. Border Styles

Set border width, style, and color.

```css
.box {
  border: 4px solid #333;
}
```
**Styles:**  
- `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`, `none`, `hidden`

**Shorthand:**
```css
border: 2px dashed #e91e63;
```
Or set each side:
```css
border-top: 2px solid #e91e63;
border-right: 1px dotted #f44336;
```

---

### b. Border Radius (Rounded Corners)

Make element corners rounded.

```css
.card {
  border-radius: 12px;
}
```
- `border-radius: 50%;` makes a perfect circle (if width and height are equal).
- You can use 1-4 values for different corners:
  ```css
  border-radius: 10px 20px 30px 40px; /* top-left, top-right, bottom-right, bottom-left */
  ```

---

### c. Box Shadows

Add shadow effects to elements for depth and emphasis.

```css
.shadow {
  box-shadow: 4px 4px 16px rgba(0,0,0,0.2);
}
```
- Syntax: `offset-x offset-y blur-radius color`
- Optional: `spread-radius` and `inset`

**Examples:**
```css
/* Simple shadow */
.box {
  box-shadow: 2px 2px 8px #888;
}

/* Multiple shadows */
.box {
  box-shadow: 1px 1px 8px #888, 0 0 2px #222;
}

/* Inset shadow */
.box {
  box-shadow: inset 2px 2px 5px #555;
}
```

---

## 3. Full Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Backgrounds & Borders Example</title>
    <style>
      body {
        background: linear-gradient(120deg, #f5f7fa, #c3cfe2);
        font-family: Arial, sans-serif;
      }
      .profile-card {
        background: #fff;
        width: 340px;
        margin: 40px auto;
        padding: 24px;
        border: 3px solid #2196f3;
        border-radius: 18px;
        box-shadow: 0 8px 24px rgba(33,150,243,0.15);
        text-align: center;
      }
      .avatar {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        border: 4px solid #e1bee7;
        box-shadow: 0 4px 12px #a18cd1;
        background: radial-gradient(circle, #fbc2eb, #a6c1ee);
      }
      .gradient-btn {
        background: linear-gradient(90deg, #ff9800, #f44336);
        color: white;
        border: none;
        border-radius: 24px;
        padding: 12px 32px;
        font-size: 1.1em;
        cursor: pointer;
        box-shadow: 2px 4px 16px rgba(244,67,54,0.2);
        margin-top: 18px;
        transition: box-shadow 0.2s;
      }
      .gradient-btn:hover {
        box-shadow: 2px 6px 32px rgba(255,152,0,0.3);
      }
      .dashed-box {
        border: 2px dashed #e91e63;
        margin: 24px 0;
        padding: 12px;
        background: repeating-linear-gradient(
          45deg, #fceabb, #fceabb 10px, #f8b500 10px, #f8b500 20px
        );
      }
    </style>
  </head>
  <body>
    <div class="profile-card">
      <img src="https://i.pravatar.cc/100?img=3" class="avatar" alt="Profile photo">
      <h2>Jane Doe</h2>
      <p>Front-end Developer</p>
      <button class="gradient-btn">Contact Me</button>
      <div class="dashed-box">
        <b>Fun Fact:</b> I love CSS gradients! 🌈
      </div>
    </div>
  </body>
</html>
```

---

## 4. Best Practices

- Use gradients for modern, scalable backgrounds without images.
- Prefer border-radius for subtle, modern UI.
- Use box-shadow for emphasis and depth, but avoid overusing for better performance and design clarity.
- Combine background and border techniques for unique effects.

---

## 🎯 Task Checklist

- [x] Use `background-color`, `background-image`, and at least one gradient.
- [x] Apply at least 2 different border styles.
- [x] Add rounded corners to an element with `border-radius`.
- [x] Add a box shadow to a button or card.
- [x] Experiment with background properties (repeat, position, size).

---

**Excellent! You now know how to make your pages stand out with backgrounds and borders. Next, you'll learn about layout techniques like Flexbox and Grid!**