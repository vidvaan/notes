# Day 5: Forms

Welcome to Day 5! Today, you'll learn how to create interactive forms in HTML. Forms are essential for collecting user input, such as login information, feedback, surveys, and more.

---

## 1. Basic Form Structure

Forms are created using the `<form>` tag. This tag can include various input elements.  
Common form attributes:
- `action`: The URL where the form data will be sent.
- `method`: The HTTP method used when submitting the form (`get` or `post`).

**Example:**
```html
<form action="/submit" method="post">
  <!-- Form elements go here -->
</form>
```

---

## 2. Input Fields

The `<input>` element is used for different types of user input.  
Common `type` values:
- `text`: Single-line text
- `email`: Email address
- `password`: Password field (masks input)
- `number`: Numeric input
- `checkbox`: Checkbox
- `radio`: Radio button
- `date`: Date picker
- `file`: File upload

**Example:**
```html
<label for="username">Username:</label>
<input type="text" id="username" name="username" placeholder="Enter your username" required>

<label for="email">Email:</label>
<input type="email" id="email" name="email" placeholder="Enter your email" required>

<label for="birthdate">Birthdate:</label>
<input type="date" id="birthdate" name="birthdate">

<label for="profilePic">Upload Profile Picture:</label>
<input type="file" id="profilePic" name="profilePic">
```

---

## 3. Textarea

Use `<textarea>` for multi-line text input, like comments or messages.

**Example:**
```html
<label for="message">Your Message:</label>
<textarea id="message" name="message" rows="4" cols="40" placeholder="Type your message here"></textarea>
```

---

## 4. Buttons

The `<button>` tag creates clickable buttons, commonly used for submitting or resetting forms.

- **Submit button:** Submits the form data
- **Reset button:** Clears all form fields
- **Button type:** Use `type="button"` for a button that does not submit the form

**Example:**
```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
<button type="button" onclick="alert('You clicked me!')">Click Me</button>
```

---

## 5. Select & Option (Dropdown Menus)

Use `<select>` for dropdown menus and `<option>` for each selectable item.

**Example:**
```html
<label for="country">Country:</label>
<select id="country" name="country">
  <option value="">--Select your country--</option>
  <option value="us">United States</option>
  <option value="uk">United Kingdom</option>
  <option value="in">India</option>
</select>
```

---

## 6. Radio Buttons and Checkboxes

- **Radio buttons:** Allow one selection from a group (use the same `name` for grouping)
- **Checkboxes:** Allow multiple selections independently

**Example:**
```html
<p>Gender:</p>
<input type="radio" id="male" name="gender" value="male">
<label for="male">Male</label>
<input type="radio" id="female" name="gender" value="female">
<label for="female">Female</label>

<p>Select your hobbies:</p>
<input type="checkbox" id="reading" name="hobbies" value="reading">
<label for="reading">Reading</label>
<input type="checkbox" id="sports" name="hobbies" value="sports">
<label for="sports">Sports</label>
<input type="checkbox" id="music" name="hobbies" value="music">
<label for="music">Music</label>
```

---

## 7. Form Attributes & Field Attributes

- `required`: Field must be filled out before submitting
- `placeholder`: Hint for expected input
- `min`, `max`, `maxlength`, `pattern`: Restrict input values
- `disabled`, `readonly`: Make a field uneditable

**Example:**
```html
<input type="text" name="username" placeholder="Username" required minlength="4" maxlength="12">
<input type="number" name="age" min="1" max="120">
```

---

## 8. Grouping Form Fields with `<fieldset>` and `<legend>`

Use `<fieldset>` to group related form elements and `<legend>` to give the group a title.

**Example:**
```html
<fieldset>
  <legend>Personal Information</legend>
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname">
</fieldset>
```

---

## 9. Example: Complete Form

```html
<form action="/submit" method="post">
  <fieldset>
    <legend>Registration Form</legend>
    
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required><br><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br><br>

    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required minlength="6"><br><br>

    <label for="country">Country:</label>
    <select id="country" name="country" required>
      <option value="">--Choose--</option>
      <option value="us">United States</option>
      <option value="uk">United Kingdom</option>
      <option value="in">India</option>
    </select><br><br>

    <p>Gender:</p>
    <input type="radio" id="male" name="gender" value="male">
    <label for="male">Male</label>
    <input type="radio" id="female" name="gender" value="female">
    <label for="female">Female</label><br><br>

    <p>Hobbies:</p>
    <input type="checkbox" id="reading" name="hobbies" value="reading">
    <label for="reading">Reading</label>
    <input type="checkbox" id="sports" name="hobbies" value="sports">
    <label for="sports">Sports</label>
    <input type="checkbox" id="music" name="hobbies" value="music">
    <label for="music">Music</label><br><br>

    <label for="bio">Short Bio:</label><br>
    <textarea id="bio" name="bio" rows="3" placeholder="Tell us about yourself"></textarea><br><br>

    <button type="submit">Register</button>
    <button type="reset">Reset</button>
  </fieldset>
</form>
```

---

## 🎯 Task Checklist

- [x] Create a form with at least three types of input (text, password, email, etc.)
- [x] Use textarea, select, radio, and checkbox elements
- [x] Add placeholder, required, and min/max/length attributes
- [x] Use `<fieldset>` and `<legend>` to group related fields
- [x] Experiment with a submit and reset button
- [x] Try submitting your form (action can be a test URL or "#")

---

**Excellent work! You’ve now learned how to build rich, interactive forms for your websites. Tomorrow you’ll dive into semantic HTML and page structure!**