# Day 25: Forms & Validation

Welcome to Day 25! Today you’ll learn how to work with HTML forms in JavaScript: accessing values entered by the user, and performing simple validation before submitting data.

---

## 1. Accessing Form Values

You can access form input values using JavaScript in several ways:

### a. By Element ID

```html
<input id="username" type="text" />
<button onclick="showValue()">Show Value</button>
<script>
  function showValue() {
    const value = document.getElementById('username').value;
    alert("You entered: " + value);
  }
</script>
```

### b. Using the `form` Object

```html
<form id="myForm">
  <input name="email" type="email" />
  <button type="button" onclick="getEmail()">Get Email</button>
</form>
<script>
  function getEmail() {
    const email = document.forms['myForm']['email'].value;
    alert("Email: " + email);
  }
</script>
```

---

## 2. Basic Client-Side Validation

Client-side validation checks user input **before** sending data to the server.  
This makes your app more user-friendly and helps prevent errors.

### a. Example: Required Field Validation

```html
<form id="loginForm" onsubmit="return validateForm()">
  <input id="user" type="text" placeholder="Username" />
  <input id="pass" type="password" placeholder="Password" />
  <button type="submit">Login</button>
  <div id="error" style="color:red;"></div>
</form>
<script>
  function validateForm() {
    const user = document.getElementById('user').value.trim();
    const pass = document.getElementById('pass').value.trim();
    if (user === "" || pass === "") {
      document.getElementById('error').textContent = "All fields are required.";
      return false; // Prevent form submission
    }
    // Clear error and allow submission
    document.getElementById('error').textContent = "";
    return true;
  }
</script>
```

---

### b. Example: Email Format Validation

```html
<form id="emailForm" onsubmit="return checkEmail()">
  <input id="emailInput" type="email" placeholder="Enter your email" />
  <button type="submit">Submit</button>
  <div id="emailError" style="color:red;"></div>
</form>
<script>
  function checkEmail() {
    const email = document.getElementById('emailInput').value.trim();
    // Simple email regex
    const emailPattern = /^[^@\s]+@[^@\s]+\.[^@\s]+$/;
    if (!emailPattern.test(email)) {
      document.getElementById('emailError').textContent = "Please enter a valid email address.";
      return false;
    }
    document.getElementById('emailError').textContent = "";
    return true;
  }
</script>
```

---

### c. Example: Preventing Form Submission

If validation fails, returning `false` from the `onsubmit` handler prevents the form from submitting and reloading the page.

---

## 3. Putting It All Together: Full Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Form Validation Example</title>
    <style>
      body { font-family: Arial, sans-serif; }
      .form-group { margin-bottom: 10px; }
      .error { color: red; }
    </style>
  </head>
  <body>
    <h2>Register</h2>
    <form id="regForm" onsubmit="return validateRegistration()">
      <div class="form-group">
        <input id="regUser" type="text" placeholder="Username" />
      </div>
      <div class="form-group">
        <input id="regEmail" type="email" placeholder="Email" />
      </div>
      <div class="form-group">
        <input id="regPass" type="password" placeholder="Password" />
      </div>
      <button type="submit">Register</button>
      <div id="regError" class="error"></div>
    </form>
    <script>
      function validateRegistration() {
        const user = document.getElementById('regUser').value.trim();
        const email = document.getElementById('regEmail').value.trim();
        const pass = document.getElementById('regPass').value.trim();
        const emailPattern = /^[^@\s]+@[^@\s]+\.[^@\s]+$/;

        if (!user || !email || !pass) {
          document.getElementById('regError').textContent = "All fields are required.";
          return false;
        }
        if (!emailPattern.test(email)) {
          document.getElementById('regError').textContent = "Enter a valid email.";
          return false;
        }
        document.getElementById('regError').textContent = "";
        alert("Registration successful!");
        return true;
      }
    </script>
  </body>
</html>
```

---

## 4. Best Practices

- Always validate user input on the client side for better UX.
- **Never** rely solely on client-side validation for security—always validate on the server too.
- Use `.trim()` to remove extra spaces from input.
- Show clear error messages to help users fix their input.
- Use HTML5 input types (`type="email"`, `type="number"`, etc.) for basic browser validation.

---

## 🎯 Task Checklist

- [x] Access form values with JavaScript.
- [x] Validate required fields before submit.
- [x] Validate email format.
- [x] Show error messages for invalid input.

---

**Great job! Now you can create interactive, user-friendly forms with JavaScript validation.**