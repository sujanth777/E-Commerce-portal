<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>E-Commerce Portal</title>
  <style>
    /* Basic styling */
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f7f7f7; }
    header { background: #2874f0; color: white; padding: 10px 20px; }
    nav ul { list-style: none; padding: 0; margin: 0; display: flex; }
    nav ul li { margin-right: 20px; }
    nav ul li a { color: white; text-decoration: none; font-weight: bold; }
    nav ul li a:hover { text-decoration: underline; }
    main { max-width: 1000px; margin: 20px auto; background: white; padding: 20px; border-radius: 5px; }
    section { margin-bottom: 40px; }
    h1, h2, h3, h4 { color: #2874f0; margin-bottom: 10px; }
    input, button { padding: 8px; margin: 5px 0; width: 100%; max-width: 300px; }
    label { display: block; margin-top: 10px; }
    .error { color: red; font-size: 0.9em; }
    .list-item { background: #eaeaea; margin: 8px 0; padding: 10px; border-radius: 4px; }
  </style>
</head>
<body>

<header>
  <nav>
    <ul>
      <li><h2><a href="#home">Home</a></h2></li>
      <li><h2><a href="#products">Product Items</a></h2></li>
      <li><h2><a href="#contact">Contact Us</a></h2></li>
      <li><h2><a href="#about">About Us</a></h2></li>
    </ul>
  </nav>
</header>

<main>
  <section id="home">
    <h1>Welcome to Our E-Commerce Portal</h1>
    <h2>Shop your favorite products easily!</h2>
  </section>

  <section id="registration">
    <h1>User Registration</h1>
    <form id="registrationForm" novalidate>
      <h3><label for="regUsername">Username:</label></h3>
      <input type="text" id="regUsername" name="username" required />
      <div class="error" id="regUsernameError"></div>

      <h3><label for="regEmail">Email:</label></h3>
      <input type="email" id="regEmail" name="email" required />
      <div class="error" id="regEmailError"></div>

      <h3><label for="regPassword">Password:</label></h3>
      <input type="password" id="regPassword" name="password" required minlength="6" />
      <div class="error" id="regPasswordError"></div>

      <h3><label for="regConfirmPassword">Confirm Password:</label></h3>
      <input type="password" id="regConfirmPassword" name="confirmPassword" required />
      <div class="error" id="regConfirmPasswordError"></div>

      <button type="submit">Register</button>
    </form>
  </section>

  <section id="login">
    <h1>User Login</h1>
    <form id="loginForm" novalidate>
      <h3><label for="loginEmail">Email:</label></h3>
      <input type="email" id="loginEmail" name="email" required />
      <div class="error" id="loginEmailError"></div>

      <h3><label for="loginPassword">Password:</label></h3>
      <input type="password" id="loginPassword" name="password" required />
      <div class="error" id="loginPasswordError"></div>

      <button type="submit">Login</button>
    </form>
  </section>

  <section id="orders">
    <h1>Orders List</h1>
    <h4>Order #1234 - Delivered</h4>
    <h4>Order #5678 - In Transit</h4>
  </section>

  <section id="wishlist">
    <h1>Wishlist</h1>
    <h4>Smartphone XYZ</h4>
    <h4>Headphones ABC</h4>
  </section>

  <section id="comments">
    <h1>Comments & Reviews</h1>
    <h4><strong>John Doe:</strong> Great product!</h4>
    <h4><strong>Jane Smith:</strong> Fast delivery and good packaging.</h4>
  </section>

  <section id="customer-care">
    <h1>Customer Care</h1>
    <h2>Contact Information</h2>
    <p>For support, contact us at support@example.com or call 123-456-7890</p>
  </section>

  <section id="reporting">
    <h1>Reporting Options</h1>
    <h2>Report Issues</h2>
    <p>If you want to report a problem with an order or product, please contact support@example.com with details.</p>
  </section>
</main>

<script>
  const regForm = document.getElementById('registrationForm');
  regForm.addEventListener('submit', function(e) {
    e.preventDefault();
    let valid = true;

    const username = regForm.username.value.trim();
    if (!username) {
      document.getElementById('regUsernameError').textContent = "Username is required.";
      valid = false;
    } else {
      document.getElementById('regUsernameError').textContent = "";
    }

    const email = regForm.email.value.trim();
    const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!email) {
      document.getElementById('regEmailError').textContent = "Email is required.";
      valid = false;
    } else if (!emailPattern.test(email)) {
      document.getElementById('regEmailError').textContent = "Enter a valid email.";
      valid = false;
    } else {
      document.getElementById('regEmailError').textContent = "";
    }

    const password = regForm.password.value;
    if (!password) {
      document.getElementById('regPasswordError').textContent = "Password is required.";
      valid = false;
    } else if (password.length < 6) {
      document.getElementById('regPasswordError').textContent = "Password must be at least 6 characters.";
      valid = false;
    } else {
      document.getElementById('regPasswordError').textContent = "";
    }

    const confirmPassword = regForm.confirmPassword.value;
    if (confirmPassword !== password) {
      document.getElementById('regConfirmPasswordError').textContent = "Passwords do not match.";
      valid = false;
    } else {
      document.getElementById('regConfirmPasswordError').textContent = "";
    }

    if (valid) {
      alert("Registration successful!");
      regForm.reset();
    }
  });

  const loginForm = document.getElementById('loginForm');
  loginForm.addEventListener('submit', function(e) {
    e.preventDefault();
    let valid = true;

    const email = loginForm.email.value.trim();
    const password = loginForm.password.value;

    if (!email) {
      document.getElementById('loginEmailError').textContent = "Email is required.";
      valid = false;
    } else {
      document.getElementById('loginEmailError').textContent = "";
    }

    if (!password) {
      document.getElementById('loginPasswordError').textContent = "Password is required.";
      valid = false;
    } else {
      document.getElementById('loginPasswordError').textContent = "";
    }

    if (valid) {
      alert("Login successful!");
      loginForm.reset();
    }
  });
</script>

</body>
</html>
