# Day 7: Mini Project

Congratulations on reaching Day 7! Today, you’ll put your new HTML skills to the test by building a simple **profile** or **portfolio** page using only HTML. This project will help you practice using headings, paragraphs, images, links, lists, tables, forms, and semantic tags.

---

## Project Requirements

- Use headings for your name and section titles.
- Add a short paragraph introducing yourself.
- Include a profile picture (use a local image or a placeholder URL).
- Add a table or list to showcase your skills or interests.
- Create links to your social profiles (e.g., LinkedIn, GitHub).
- Use semantic tags such as `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
- Optionally, add a simple contact form (name, email, message—no CSS or backend needed).

---

## Example Structure

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My Profile Page</title>
  </head>
  <body>
    <header>
      <h1>Jane Doe</h1>
      <nav>
        <a href="#about">About</a> |
        <a href="#skills">Skills</a> |
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <section id="about">
        <h2>About Me</h2>
        <img src="https://via.placeholder.com/150" alt="Profile Picture">
        <p>
          Hello! I'm Jane, a passionate web developer learning HTML, CSS, and JavaScript.<br>
          I love building websites and learning new technologies.
        </p>
      </section>

      <section id="skills">
        <h2>My Skills</h2>
        <ul>
          <li>HTML</li>
          <li>CSS (coming soon!)</li>
          <li>JavaScript (coming soon!)</li>
        </ul>
        <!-- Or you can use a table:
        <table>
          <tr><th>Skill</th><th>Level</th></tr>
          <tr><td>HTML</td><td>Beginner</td></tr>
          <tr><td>CSS</td><td>Learning</td></tr>
        </table>
        -->
      </section>

      <section>
        <h2>Links</h2>
        <ul>
          <li><a href="https://github.com/yourusername" target="_blank">GitHub</a></li>
          <li><a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a></li>
        </ul>
      </section>

      <section id="contact">
        <h2>Contact Me</h2>
        <form>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name"><br><br>
          <label for="email">Email:</label>
          <input type="email" id="email" name="email"><br><br>
          <label for="message">Message:</label><br>
          <textarea id="message" name="message" rows="4" cols="30"></textarea><br><br>
          <button type="submit">Send</button>
        </form>
      </section>
    </main>

    <footer>
      <p>&copy; 2025 Jane Doe</p>
    </footer>
  </body>
</html>
```

---

## Tips

- Save your file as `index.html`.
- Replace placeholder text and links with your real information.
- Use other elements you’ve learned: lists, tables, images, etc.
- Don’t worry about design or CSS yet—focus on structure and practicing HTML tags.

---

## 🎯 Task Checklist

- [x] Create a new HTML file for your profile or portfolio.
- [x] Use headings, paragraphs, lists/tables, images, and links.
- [x] Structure your page with semantic HTML tags.
- [x] (Optional) Add a basic contact form.

---

**Well done! You’ve completed your first mini project. Next week, you’ll start learning how to style your page using CSS.**