4) Write JavaScript to validate the following fields of the Registration page
   <!DOCTYPE html>
<html>
<body>
<h2>Registration</h2>
<form onsubmit="return validate()">
  Name: <input id="name"><br><br>
  Password: <input type="password" id="pass"><br><br>
  Email: <input id="email"><br><br>
  Mobile: <input id="mobile"><br><br>
  Address: <input id="addr"><br><br>
  <button type="submit">Register</button>
</form>

<script>
function validate() {
  let name = document.getElementById("name").value;
  let pass = document.getElementById("pass").value;
  let email = document.getElementById("email").value;
  let mobile = document.getElementById("mobile").value;
  let addr = document.getElementById("addr").value;

  if (!/^[A-Za-z]{6,}$/.test(name)) {
    alert("Name must be only letters and at least 6 characters long");
    return false;
  }
  if (pass.length < 6) {
    alert("Password must be at least 6 characters long");
    return false;
  }
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
    alert("Invalid email format");
    return false;
  }
  if (!/^\d{10}$/.test(mobile)) {
    alert("Mobile number must be exactly 10 digits");
    return false;
  }
  if (!addr.trim()) {
    alert("Address is required");
    return false;
  }

  alert("Registration successful!");
  return true;
}
</script>
</body>
</html>
5>Develop and demonstrate JavaScript with POP-UP boxes and functions for the following problems:
a.	Input: Click on Display Date button using on click( ) function Output: Display date in the textbox.
b.	Input: A number n obtained using prompt Output: Factorial of n number using alert.
  <!DOCTYPE html>
<html>
<head>
    <title>JavaScript Pop-up Examples</title>
</head>
<body>

<!-- a. Display Date -->
<h3>a. Display Date in Textbox</h3>
<input type="text" id="dateBox" readonly>
<button onclick="showDate()">Display Date</button>

<!-- b. Factorial -->
<h3>b. Factorial using Prompt & Alert</h3>
<button onclick="findFactorial()">Find Factorial</button>

<script>
    // a. Function to display date
    function showDate() {
        let today = new Date(); // get current date & time
        document.getElementById("dateBox").value = today; // show in textbox
    }

    // b. Function to find factorial
    function findFactorial() {
        let n = prompt("Enter a number:"); // take input
        n = Number(n); // convert to number
        if (isNaN(n) || n < 0) {
            alert("Please enter a valid non-negative number.");
            return;
        }
        let fact = 1;
        for (let i = 1; i <= n; i++) {
            fact *= i;
        }
        alert("Factorial of " + n + " is " + fact);
    }
</script>

</body>
</html>
6>Write a JavaScript program to generate a for loop that will iterate from 0 to 15. For each iteration, it will check if the current number is odd or even, and display a message to the screen using map and filters.
const numbers = Array.from({ length: 16 }, (_, i) => i);

const evenMessages = numbers.filter(n => n % 2 === 0).map(n => `${n} is even`);
const oddMessages = numbers.filter(n => n % 2 !== 0).map(n => `${n} is odd`);

[...evenMessages, ...oddMessages].forEach(msg => console.log(msg));
7> Write a JavaScript program that modifies the DOM to change the content of an HTML element. Add event listeners to handle button clicks and dynamically change text on the page
<!DOCTYPE html>
<html>
<body>
  <p id="demo">Hello World!</p>
  <button id="changeTextButton">Change Text</button>

  <script>
    document.getElementById("changeTextButton").addEventListener("click", function() {
      document.getElementById("demo").innerHTML = "Text changed!";
    });
  </script>
</body>
</html>
8> Write a JavaScript program that handles events triggered by the body, button, text box, and password field
<!DOCTYPE html>
<html>
<head>
    <title>Events Example</title>
    <script>
        function bodyEvent() {
            alert("Body Loaded");
        }
        function btnEvent() {
            alert("Button Clicked");
        }
        function textEvent() {
            alert("Text Changed");
        }
        function passEvent() {
            alert("Password Focused");
        }
    </script>
</head>
<body onload="bodyEvent()">

    Name: <input type="text" onchange="textEvent()"><br><br>
    Password: <input type="password" onfocus="passEvent()"><br><br>
    <button onclick="btnEvent()">Click</button>

</body>
</html>


