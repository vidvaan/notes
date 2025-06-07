# Day 3: Links & Images

Welcome to Day 3! Today, you'll learn how to add links and images to your web pages using HTML. These elements help connect your site to other resources and make your pages visually engaging.

---

## 1. Anchor Tags (Links)

Use the `<a>` tag (anchor tag) to create hyperlinks.

**Basic Example:**
```html
<a href="https://www.example.com">Visit Example.com</a>
```

### Absolute vs. Relative Links

- **Absolute Link:** Points to an external site or resource using the full URL.
  ```html
  <a href="https://www.google.com">Google</a>
  ```

- **Relative Link:** Points to a file or page within your own website/project folder.
  ```html
  <a href="about.html">About Us</a>
  ```

**Open link in new tab:**
```html
<a href="https://www.example.com" target="_blank">Open in new tab</a>
```

---

## 2. Adding Images

Use the `<img>` tag to display images.

**Basic Syntax:**
```html
<img src="image.jpg" alt="Description of image">
```
- `src`: The path or URL to the image file.
- `alt`: Alternative text shown if the image can't load (important for accessibility).

### Example with local image:
```html
<img src="images/logo.png" alt="Company Logo">
```

### Example with external image:
```html
<img src="https://www.example.com/image.jpg" alt="Sample Image">
```

---

## 3. Alt Attributes

The `alt` attribute provides a text description for the image:
- Helps visually impaired users understand the content.
- Displays if the image cannot be loaded.

**Example:**
```html
<img src="dog.jpg" alt="A smiling brown dog">
```

---

## 4. Image Formats

Common image formats for the web:
- `.jpg` or `.jpeg`: Good for photographs (lossy compression).
- `.png`: Supports transparency, good for graphics and logos.
- `.gif`: Simple animations, limited colors.
- `.svg`: Scalable vector graphics, ideal for icons and logos.

---

## 🎯 Task Checklist

- [x] Add absolute and relative links to your HTML file.
- [x] Create links that open in a new tab.
- [x] Add images using both local files and external URLs.
- [x] Use descriptive alt text for your images.
- [x] Try using different image formats.

---

**Great work! You've now learned how to connect pages and add images to your websites. Tomorrow you'll learn about tables!**