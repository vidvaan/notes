# Day 6: Semantic HTML

Welcome to Day 6! Today, you'll learn about **semantic HTML**—a fundamental concept for writing clean, accessible, and well-structured web pages.

---

## 1. What is Semantic HTML?

**Semantic HTML** means using HTML tags that convey the _meaning_ of the content they enclose, not just how it looks. Semantic tags describe their intended purpose, which helps browsers, search engines, screen readers, and developers better understand the structure of your web page.

---

## 2. Why Do Semantic Tags Matter?

- **Accessibility:** Semantic tags help screen readers and assistive technologies interpret your content correctly, making your site more usable for everyone.
- **SEO:** Search engines use semantic tags to better index your content, improving your site’s visibility in search results.
- **Maintainability:** Semantic code is easier to read, maintain, and collaborate on, as the purpose of each section is clear.
- **Standardization:** Using the right tags helps ensure your site behaves as expected across different browsers and devices.

---

## 3. Common Semantic HTML Tags

### `<header>`

Defines the introductory content or navigational links for a section or the entire page.

```html
<header>
  <h1>My Blog</h1>
  <p>Welcome to my awesome blog!</p>
</header>
```

### `<nav>`

Wraps navigation links. There can be multiple `<nav>` elements on a page if needed (e.g., main nav and footer nav).

```html
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#articles">Articles</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

### `<main>`

Represents the dominant content of the `<body>`. There should be only one `<main>` per page.

```html
<main>
  <h2>Latest Articles</h2>
  <!-- Articles go here -->
</main>
```

### `<section>`

Defines a thematic grouping of content, typically with a heading. Use it to break your page into logical parts.

```html
<section>
  <h3>About Me</h3>
  <p>I am a web developer...</p>
</section>
```

### `<article>`

Encapsulates a self-contained composition that could stand alone, such as a blog post, news story, or forum post.

```html
<article>
  <h2>How to Learn HTML</h2>
  <p>Start by understanding the basics...</p>
</article>
```

### `<aside>`

Contains content indirectly related to the main content, like sidebars, pull quotes, or additional info.

```html
<aside>
  <h4>Did you know?</h4>
  <p>You can learn HTML in just a few weeks!</p>
</aside>
```

### `<footer>`

Includes footer information for a section or the whole page, such as copyright, contact info, or related links.

```html
<footer>
  <p>&copy; 2025 My Blog. All rights reserved.</p>
</footer>
```

---

## 4. Example: Semantic HTML Page Structure

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Semantic HTML Example</title>
  </head>
  <body>
    <header>
      <h1>Web Dev Journey</h1>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Blog</a></li>
          <li><a href="#">About</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section>
        <h2>Featured Article</h2>
        <article>
          <h3>Why Use Semantic HTML?</h3>
          <p>Semantic HTML improves accessibility, SEO, and code readability...</p>
        </article>
      </section>
      <aside>
        <h4>Tip</h4>
        <p>Use semantic tags to make your markup meaningful!</p>
      </aside>
    </main>

    <footer>
      <p>Contact: info@webdevjourney.com</p>
      <p>&copy; 2025 Web Dev Journey</p>
    </footer>
  </body>
</html>
```

---

## 5. Best Practices

- Use semantic tags whenever possible instead of generic `<div>` and `<span>` for structure.
- Each page should have **one** `<main>`, but can have multiple `<section>`, `<article>`, `<aside>`, etc.
- Add headings inside your semantic sections for clarity.
- Nest semantic elements appropriately (e.g., `<nav>` inside `<header>`, `<article>` inside `<section>`).

---

## 🎯 Task Checklist

- [x] Refactor an existing HTML page to use semantic tags.
- [x] Create a new page using `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, and `<footer>`.
- [x] Add real or sample content to each section.
- [x] Validate your HTML for semantic correctness (try [W3C Validator](https://validator.w3.org/)).

---

**Great job! Semantic HTML is the backbone of modern, accessible web design. Tomorrow, you’ll start learning CSS to style your pages!**