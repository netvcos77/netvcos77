- 👋 Hi, I’m @netvcos77
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
netvcos77/netvcos77 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---><!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Signup Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Signup Page</h1>
        <form id="signupForm">
            <input type="text" id="username" placeholder="Username" required><br>
            <input type="email" id="email" placeholder="Email" required><br>
            <input type="password" id="password" placeholder="Password" required><br>
            <button type="submit">Sign Up</button>
        </form>
        <button id="logoutButton" style="display:none;" onclick="logout()">Logout</button>
    </div>

    <script src="scripts.js"></script>
</body>
</html>
/* styles.css */
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f4f4f4;
}

.container {
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    text-align: center;
    width: 300px;
}

input {
    width: 80%;
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    border: 1px solid #ccc;
}

button {
    width: 80%;
    padding: 10px;
    border-radius: 5px;
    border: none;
    background-color: #4CAF50;
    color: white;
    font-size: 16px;
}

button:hover {
    background-color: #45a049;
}

#logoutButton {
    background-color: #f44336;
}

#logoutButton:hover {
    background-color: #e53935;
}// scripts.js

// Check if the user is already logged in
document.addEventListener("DOMContentLoaded", function () {
    if (localStorage.getItem("loggedIn")) {
        document.getElementById("logoutButton").style.display = "inline-block";
        document.getElementById("signupForm").style.display = "none";
    } else {
        document.getElementById("logoutButton").style.display = "none";
        document.getElementById("signupForm").style.display = "block";
    }
});

// Logout function
function logout() {
    // Clear the session (or you can use sessionStorage if you'd prefer)
    localStorage.removeItem("loggedIn");
    
    // Hide logout button and show the signup form again
    document.getElementById("logoutButton").style.display = "none";
    document.getElementById("signupForm").style.display = "block";
    
    // Optionally, show a message to the user
    alert("You have successfully logged out.");
}

// Signup form submission logic (simulated)
document.getElementById("signupForm").addEventListener("submit", function (event) {
    event.preventDefault(); // Prevent the form from submitting in the default way

    // Simulate a successful signup and login process
    const username = document.getElementById("username").value;
    const email = document.getElementById("email").value;
    const password = document.getElementById("password").value;

    // You can replace this with actual signup logic (e.g., sending data to a backend)
    if (username && email && password) {
        // Simulate that the user is logged in by setting a flag in localStorage
        localStorage.setItem("loggedIn", true);
        
        // Hide the signup form and show the logout button
        document.getElementById("signupForm").style.display = "none";
        document.getElementById("logoutButton").style.display = "inline-block";
    } else {
        alert("Please fill in all fields.");
    }
});


