# Ex.08 Design of a Standard Calculator
## Date:04-11-23

## AIM:
To design a web application for a standard calculator with minimum five operations.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for creating attractive colors.

### Step 4:
Write JavaScript program for implementing five different operations.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html>
  <head>
    <title>Simple Calculator</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
      }

      #calculator-container {
        background-color: #f0f0f0;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        width: 300px; /* Adjust container width for better alignment */
      }

      input[type="text"] {
        width: calc(100% - 20px); /* Adjust input width and add padding */
        padding: 10px;
        margin: 5px 0;
        color: black;
        font-size: 16px; /* Change font size for better fit */
      }

      table {
        margin-top: 10px;
        width: 100%; /* Ensure the table takes full width */
      }

      td {
        text-align: center; /* Center align the buttons */
        padding: 5px; /* Add padding for space between buttons */
      }

      button {
        padding: 10px 5px; /* Adjust button size for a more compact look */
        font-size: 16px; /* Change button font size for better fit */
        width: 100%; /* Make buttons fill the table cells */
      }
    </style>
  </head>
  <body>
    <div id="calculator-container">
      <h1>Calculator</h1>
      <input
        type="text"
        id="display"
        readonly
        onkeypress="handleKeyPress(event)"
      />
      <table>
        <tr>
          <td><button onclick="appendToDisplay('7')">7</button></td>
          <td><button onclick="appendToDisplay('8')">8</button></td>
          <td><button onclick="appendToDisplay('9')">9</button></td>
          <td>
            <button
              data-operator="/"
              onclick="appendToDisplay('/')"
              style="background-color: blue; color: white"
            >
              /
            </button>
          </td>
          <td>
            <button
              data-operator="±"
              onclick="toggleSign()"
              style="background-color: cyan; color: black"
            >
              ±
            </button>
          </td>
        </tr>
        <tr>
          <td><button onclick="appendToDisplay('4')">4</button></td>
          <td><button onclick="appendToDisplay('5')">5</button></td>
          <td><button onclick="appendToDisplay('6')">6</button></td>
          <td>
            <button
              data-operator="*"
              onclick="appendToDisplay('*')"
              style="background-color: blue; color: white"
            >
              *
            </button>
          </td>
          <td>
            <button
              data-operator="sqrt"
              onclick="calculateSquareRoot()"
              style="background-color: cyan; color: black"
            >
              √
            </button>
          </td>
        </tr>
        <tr>
          <td><button onclick="appendToDisplay('1')">1</button></td>
          <td><button onclick="appendToDisplay('2')">2</button></td>
          <td><button onclick="appendToDisplay('3')">3</button></td>
          <td>
            <button
              data-operator="-"
              onclick="appendToDisplay('-')"
              style="background-color: blue; color: white"
            >
              -
            </button>
          </td>
          <td>
            <button
              data-operator="%"
              onclick="appendToDisplay('%')"
              style="background-color: blue; color: white"
            >
              %
            </button>
          </td>
        </tr>
        <tr>
          <td><button onclick="appendToDisplay('0')">0</button></td>
          <td><button onclick="appendToDisplay('.')">.</button></td>
          <td>
            <button
              onclick="clearDisplay()"
              style="background-color: red; color: white"
            >
              C
            </button>
          </td>
          <td>
            <button
              data-operator="+"
              onclick="appendToDisplay('+')"
              style="background-color: blue; color: white"
            >
              +
            </button>
          </td>
          <td>
            <button
              onclick="calculateResult()"
              style="background-color: rgb(21, 255, 0); color: white"
            >
              =
            </button>
          </td>
        </tr>
      </table>
    </div>
    <script>
      function appendToDisplay(value) {
        document.getElementById("display").value += value;
      }

      function clearDisplay() {
        document.getElementById("display").value = "";
      }

      function calculateResult() {
        try {
          document.getElementById("display").value = eval(
            document.getElementById("display").value
          );
        } catch (error) {
          document.getElementById("display").value = "Error";
        }
      }

      function calculateSquareRoot() {
        const inputValue = document.getElementById("display").value;
        const result = Math.sqrt(parseFloat(inputValue));
        document.getElementById("display").value = result;
      }

      function toggleSign() {
        let value = document.getElementById("display").value;
        document.getElementById("display").value = -parseFloat(value);
      }
      function appendToDisplay(value) {
        document.getElementById("display").value += value;
      }

      // This function handles keyboard input
      function handleKeyPress(event) {
        const key = event.key;

        // Check if the pressed key is an operator or a digit
        if (key.match(/[0-9+\-*/.%C]/)) {
          document.getElementById("display").value += key;
        }

        if (key === "Enter") {
          calculateResult();
        }
      }
      function appendToDisplay(value) {
        document.getElementById("display").value += value;
      }

      function clearDisplay() {
        document.getElementById("display").value = "";
      }

      function calculateResult() {
        try {
          document.getElementById("display").value = eval(
            document.getElementById("display").value
          );
        } catch (error) {
          document.getElementById("display").value = "Error";
        }
      }

      function calculateSquareRoot() {
        const inputValue = document.getElementById("display").value;
        const result = Math.sqrt(parseFloat(inputValue));
        document.getElementById("display").value = result;
      }

      function toggleSign() {
        let value = document.getElementById("display").value;
        document.getElementById("display").value = -parseFloat(value);
      }

      // This function handles keyboard input
      function handleKeyPress(event) {
        // Check for Enter key to evaluate the expression
        if (event.key === "Enter") {
          calculateResult();
        }
      }

      function handleKeyDown(event) {
        // Check for Backspace key to clear the last character
        if (event.key === "Backspace") {
          const display = document.getElementById("display");
          display.value = display.value.slice(0, -1);
        }
      }
    </script>
  </body>
</html>
```
## OUTPUT:
![image](https://github.com/gifty003/Calc/assets/145822352/faf27a88-c983-4e0c-b598-0573f34d6d5f)

## RESULT:
The program for designing a standard calculator using HTML and CSS is executed successfully.
