# Day 9: Colors & Typography

Welcome to Day 9! Today, you'll learn how to make your web pages visually engaging using colors and beautiful typography. You'll discover different ways to define colors and how to control the appearance of text using CSS.

---

## 1. Color Formats in CSS

CSS offers several ways to define and apply colors:

### a. Color Names

Use simple names for basic colors.

```css
h1 {
  color: red;
  background-color: lightblue;
}
```

Some common color names: `red`, `green`, `blue`, `black`, `white`, `gray`, `yellow`, `orange`, `purple`, `pink`, `teal`, `navy`.

---

### b. Hexadecimal (Hex) Codes

Hex codes are six-digit codes preceded by `#`. Each pair represents red, green, and blue.

```css
p {
  color: #ff6347;    /* tomato */
  background-color: #222222;
}
```

- Shortened 3-digit form: `#fff` (same as `#ffffff` for white).
- Range: `00` to `ff` (0-255 in hex).

---

### c. RGB and RGBA

**RGB** stands for Red, Green, Blue. Each value ranges from 0 to 255.

```css
div {
  color: rgb(0, 128, 255); /* bright blue */
}
```

**RGBA** adds an alpha channel for transparency (0 is fully transparent, 1 is fully opaque):

```css
div {
  background-color: rgba(0, 128, 255, 0.3); /* semi-transparent blue */
}
```

---

### d. HSL and HSLA

**HSL** stands for Hue (0–360), Saturation (0–100%), Lightness (0–100%).

```css
span {
  color: hsl(120, 100%, 25%); /* dark green */
}
```

**HSLA** adds alpha for transparency:

```css
span {
  color: hsla(120, 100%, 25%, 0.5); /* semi-transparent dark green */
}
```

---

### e. Example: Applying Color

```css
body {
  background-color: #f0f8ff;
  color: #222;
}

h1 {
  color: rgb(200, 80, 90);
}

.highlight {
  background-color: yellow;
  color: #333;
}
```

---

## 2. Typography in CSS

Typography involves controlling the appearance of text: font, size, weight, alignment, and spacing.

---

### a. Font Families

Specify a typeface for your text. Always provide a fallback list.

```css
body {
  font-family: 'Segoe UI', Arial, Helvetica, sans-serif;
}
```

- Use **web-safe fonts**: Arial, Verdana, Tahoma, Trebuchet MS, Times New Roman, Courier New, Georgia, etc.
- For custom fonts, you can use [Google Fonts](https://fonts.google.com/) or self-hosted fonts (covered later).

---

### b. Font Size

Control how large or small the text appears.

```css
h1 {
  font-size: 2.5em;   /* relative to parent/font size */
}
p {
  font-size: 18px;    /* absolute size */
}
```
- Units: `px` (pixels), `em`, `rem`, `%`, `vw` (viewport width).

---

### c. Font Weight

Set how bold or light the text is.

```css
strong {
  font-weight: bold;
}

.title {
  font-weight: 700;  /* numeric scale: 100 (thin) to 900 (black) */
}
```

---

### d. Text Alignment

Align text horizontally.

```css
h2 {
  text-align: center;
}
p {
  text-align: right;
}
```

Values: `left`, `right`, `center`, `justify`.

---

### e. Text Decoration & Transformation

- **Decoration:** underline, line-through, etc.

```css
a {
  text-decoration: none;
}

del {
  text-decoration: line-through;
}
```

- **Transformation:** uppercase, lowercase, capitalize

```css
h3 {
  text-transform: uppercase;
}
```

---

### f. Letter Spacing & Line Height

- **Letter Spacing:** space between characters

```css
h1 {
  letter-spacing: 2px;
}
```

- **Line Height:** vertical spacing between lines

```css
p {
  line-height: 1.6;
}
```

---

### g. Example: Typography Styles

```css
body {
  font-family: 'Georgia', serif;
  font-size: 16px;
  color: #222;
  background-color: #fdf6e3;
}

h1 {
  font-size: 2.2rem;
  font-weight: 800;
  text-align: center;
  letter-spacing: 1px;
}

h2 {
  font-size: 1.4rem;
  color: #d2691e;
  text-transform: capitalize;
}

p {
  line-height: 1.7;
  margin-bottom: 1em;
}

.code {
  font-family: 'Courier New', monospace;
  background: #eee;
  padding: 2px 6px;
  border-radius: 4px;
}

a {
  color: #0088cc;
  text-decoration: underline;
}
```

---

## 3. Complete Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Colors & Typography Example</title>
    <style>
      body {
        background: #f2f2f2;
        color: #222;
        font-family: 'Segoe UI', Arial, sans-serif;
        font-size: 18px;
        line-height: 1.6;
      }
      header {
        background: #222;
        color: #fff;
        text-align: center;
        padding: 2em 0;
      }
      h1 {
        color: #ff9800;
        font-size: 2.5em;
        letter-spacing: 2px;
        text-shadow: 2px 2px 0 #aaa;
      }
      .subtitle {
        color: hsl(200, 80%, 50%);
        font-weight: 400;
        font-size: 1.2em;
      }
      .profile {
        background: #fff;
        border-radius: 10px;
        padding: 2em;
        margin: 2em auto;
        max-width: 600px;
        box-shadow: 0 4px 16px rgba(0,0,0,0.07);
      }
      .highlight {
        background: #ffe082;
        color: #222;
        padding: 0.2em 0.5em;
        border-radius: 4px;
      }
      a {
        color: #e53935;
        text-decoration: none;
        font-weight: bold;
      }
      a:hover {
        text-decoration: underline;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>Jane Doe</h1>
      <div class="subtitle">Web Developer &amp; Designer</div>
    </header>
    <section class="profile">
      <h2>About Me</h2>
      <p>
        Hello! I'm <span class="highlight">Jane</span>, a passionate developer exploring the world of <span class="code">HTML</span> and <span class="code">CSS</span>.
      </p>
      <h2>Contact</h2>
      <p>
        Email: <a href="mailto:jane@example.com">jane@example.com</a>
      </p>
    </section>
  </body>
</html>
```

---

## 4. Best Practices

- Use external CSS for large projects.
- Always provide fallback fonts in `font-family`.
- Prefer relative units (`em`, `rem`) for responsive typography.
- Use hex, rgb, or hsl for precise color control.
- Maintain color contrast for accessibility.

---

## 🎯 Task Checklist

- [x] Use all four color formats (name, hex, rgb[a], hsl[a]) in your styles.
- [x] Change font family, size, weight, and text alignment of elements.
- [x] Adjust letter spacing and line height for better readability.
- [x] Style a link and a highlighted span or paragraph.

---

**Great work! Tomorrow, you’ll learn about the CSS box model and how to control element layout and spacing!**