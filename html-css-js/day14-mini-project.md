# Day 14: Mini Project

Congratulations! Today’s project is to **style your profile/portfolio page** with CSS, transforming your plain HTML into a beautiful, modern website. This project brings together everything you’ve learned about HTML and CSS over the last two weeks: semantic HTML, forms, tables, colors, typography, the box model, backgrounds, borders, positioning, Flexbox, and more.

---

## Requirements

- Semantic HTML structure (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`)
- Use headings, paragraphs, lists, images, links, a table, and a contact form
- Style all aspects of the site: colors, typography, backgrounds, borders, layout, etc.
- Responsive layout using Flexbox (or Grid if you wish)
- Visual enhancements: gradients, rounded corners, shadows
- At least 2 sections (e.g., About, Skills, Projects, Contact)

---

## Example: Complete Profile/Portfolio Website (With Table)

Below is a full example you can adapt and customize.  
**Save as `index.html`** and create a separate file called **`style.css`**.

---

### `index.html`
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Jane Doe | Portfolio</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <header>
      <nav>
        <div class="logo">Jane Doe</div>
        <ul class="nav-links">
          <li><a href="#about">About</a></li>
          <li><a href="#skills">Skills</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
      <div class="hero">
        <img src="https://i.pravatar.cc/140?img=3" alt="Jane Doe" class="avatar" />
        <h1>Hello, I'm Jane Doe</h1>
        <p>Front-End Developer & Designer</p>
      </div>
    </header>
    <main>
      <section id="about" class="card">
        <h2>About Me</h2>
        <p>
          I'm a passionate web developer with experience in building modern, responsive websites. I love turning ideas into reality using the power of HTML, CSS, and JavaScript.
        </p>
      </section>

      <section id="skills" class="card">
        <h2>Skills Table</h2>
        <table class="skills-table">
          <thead>
            <tr>
              <th>Skill</th>
              <th>Proficiency</th>
              <th>Experience (Years)</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>HTML5</td>
              <td>Expert</td>
              <td>3</td>
            </tr>
            <tr>
              <td>CSS3</td>
              <td>Advanced</td>
              <td>3</td>
            </tr>
            <tr>
              <td>JavaScript</td>
              <td>Intermediate</td>
              <td>2</td>
            </tr>
            <tr>
              <td>UI/UX Design</td>
              <td>Intermediate</td>
              <td>1</td>
            </tr>
          </tbody>
        </table>
        <h3>Other Skills</h3>
        <ul class="skills-list">
          <li>Responsive Design (Flexbox, Grid)</li>
          <li>Accessibility</li>
          <li>Version Control (Git)</li>
        </ul>
      </section>

      <section id="projects" class="card">
        <h2>Projects</h2>
        <article class="project">
          <h3>Portfolio Website</h3>
          <p>
            A modern, responsive portfolio website built using HTML5 and CSS3.  
            <a href="#">View Project</a>
          </p>
        </article>
        <article class="project">
          <h3>Blog Template</h3>
          <p>
            Clean and minimal blog template using semantic HTML and Flexbox layouts.  
            <a href="#">View Project</a>
          </p>
        </article>
      </section>

      <aside class="card">
        <h2>Connect</h2>
        <ul class="social-links">
          <li><a href="https://github.com/yourusername" target="_blank">GitHub</a></li>
          <li><a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a></li>
        </ul>
      </aside>

      <section id="contact" class="card">
        <h2>Contact Me</h2>
        <form>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required /><br />

          <label for="email">Email:</label>
          <input type="email" id="email" name="email" required /><br />

          <label for="message">Message:</label>
          <textarea id="message" name="message" rows="4" required></textarea><br />

          <button type="submit">Send Message</button>
        </form>
      </section>
    </main>
    <footer>
      <p>&copy; 2025 Jane Doe. All rights reserved.</p>
    </footer>
  </body>
</html>
```

---

### `style.css`
```css
/* Reset and base styles */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Arial, sans-serif;
  background: linear-gradient(120deg, #f5f7fa, #c3cfe2);
  color: #222;
  line-height: 1.6;
  min-height: 100vh;
}

/* Header and Navigation */
header {
  background: linear-gradient(90deg, #2196f3 60%, #e1bee7 100%);
  color: #fff;
  padding-bottom: 2em;
  box-shadow: 0 4px 16px rgba(33,150,243,0.1);
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5em 2em 0 2em;
}
.logo {
  font-size: 2em;
  font-weight: bold;
  letter-spacing: 2px;
}
.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5em;
}
.nav-links li a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1em;
  transition: color 0.2s;
}
.nav-links li a:hover {
  color: #ffd600;
}

/* Hero */
.hero {
  text-align: center;
  margin-top: 2em;
}
.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  border: 4px solid #fff;
  box-shadow: 0 6px 24px rgba(33,150,243,0.2);
  margin-bottom: 1em;
}
.hero h1 {
  font-size: 2.5em;
  letter-spacing: 1px;
  margin-bottom: 0.3em;
}
.hero p {
  font-size: 1.2em;
  font-weight: 400;
}

/* Main Content Layout */
main {
  max-width: 950px;
  margin: 2em auto;
  display: flex;
  flex-wrap: wrap;
  gap: 2em;
  justify-content: space-between;
}

/* Cards for sections */
.card {
  background: #fff;
  border-radius: 14px;
  box-shadow: 0 4px 24px rgba(0,0,0,0.05);
  padding: 2em 2em 1.5em 2em;
  flex: 1 1 360px;
  min-width: 330px;
  margin-bottom: 1em;
  transition: box-shadow 0.2s;
}
.card:hover {
  box-shadow: 0 8px 32px rgba(33,150,243,0.15);
}

/* Table Styles */
.skills-table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 1.5em;
  margin-top: 0.5em;
  background: #f6f8fa;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(33,150,243,0.08);
}
.skills-table th, .skills-table td {
  padding: 0.7em 1em;
  text-align: left;
}
.skills-table th {
  background: #2196f3;
  color: #fff;
  font-weight: 600;
  border-bottom: 2px solid #bbdefb;
}
.skills-table tr:nth-child(even) {
  background: #e3f2fd;
}
.skills-table tr:hover {
  background: #b3e5fc;
}

/* About & Skills */
.skills-list {
  list-style: none;
  padding-left: 0.5em;
}
.skills-list li {
  margin-bottom: 0.7em;
  padding-left: 1em;
  position: relative;
}
.skills-list li::before {
  content: '★';
  color: #ffd600;
  position: absolute;
  left: 0;
}

/* Projects */
.project {
  margin-bottom: 1.2em;
  padding-bottom: 1em;
  border-bottom: 1px solid #ececec;
}
.project:last-child {
  border-bottom: none;
}
.project h3 {
  color: #2196f3;
  margin-bottom: 0.3em;
}
.project a {
  color: #e91e63;
  text-decoration: underline;
  font-size: 1em;
}

/* Aside - Social Links */
aside.card {
  background: linear-gradient(120deg, #e1bee7 10%, #fff 100%);
  flex: 0 1 200px;
  min-width: 180px;
  margin-top: 1.5em;
}
.social-links {
  list-style: none;
  padding-left: 0;
  margin-top: 1em;
}
.social-links li {
  margin-bottom: 0.7em;
}
.social-links a {
  color: #7b1fa2;
  font-weight: bold;
  text-decoration: none;
  transition: color 0.2s;
}
.social-links a:hover {
  color: #2196f3;
}

/* Contact Form */
form {
  display: flex;
  flex-direction: column;
  gap: 1em;
  margin-top: 1em;
}
form label {
  font-weight: 500;
}
form input,
form textarea {
  padding: 0.7em 1em;
  border: 1.5px solid #c3cfe2;
  border-radius: 6px;
  font-size: 1em;
  background: #fafbfc;
  transition: border-color 0.2s;
}
form input:focus,
form textarea:focus {
  border-color: #2196f3;
  outline: none;
}
form button {
  align-self: flex-start;
  background: linear-gradient(90deg, #2196f3, #e1bee7);
  color: #fff;
  font-size: 1.1em;
  font-weight: 600;
  border: none;
  padding: 0.7em 1.8em;
  border-radius: 24px;
  box-shadow: 0 2px 8px rgba(33,150,243,0.1);
  cursor: pointer;
  transition: background 0.2s, box-shadow 0.2s;
}
form button:hover {
  background: linear-gradient(90deg, #1976d2, #8e24aa);
  box-shadow: 0 6px 16px rgba(33,150,243,0.18);
}

/* Footer */
footer {
  text-align: center;
  background: #222;
  color: #fff;
  padding: 1.2em 0;
  font-size: 1em;
  letter-spacing: 1px;
  margin-top: 3em;
  border-radius: 20px 20px 0 0;
  box-shadow: 0 -4px 12px rgba(33,150,243,0.08);
}

/* Responsive Design */
@media (max-width: 1050px) {
  main {
    flex-direction: column;
    align-items: stretch;
  }
  aside.card {
    order: 3;
    margin-bottom: 2em;
  }
}

@media (max-width: 600px) {
  nav {
    flex-direction: column;
    gap: 1em;
    padding: 1em;
  }
  .hero h1 {
    font-size: 2em;
  }
  .card {
    padding: 1.2em 0.7em;
    min-width: 0;
  }
  .skills-table th, .skills-table td {
    padding: 0.4em 0.5em;
    font-size: 0.95em;
  }
}
```

---

## 🎯 Task Checklist

- [x] Use semantic HTML tags and a clear site structure
- [x] Style with external CSS, using colors, backgrounds, borders, gradients, and shadows
- [x] Use Flexbox for responsive layout
- [x] Add a styled navigation bar and hero section
- [x] Present skills in a styled HTML table
- [x] Include a styled contact form
- [x] Make it look great on desktop and mobile

---

**Now you have a complete professional-looking portfolio site with a table!  
You’re ready to move on to advanced CSS or start learning JavaScript.**