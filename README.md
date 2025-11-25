# Ex04 Simple Calculator - React Project
## Date:24.09.2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
### App.jsx
```js
import React, { useState } from "react";
import "./App.css";

function App() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleCalculate = () => {
    try {
      setInput(String(eval(input)));
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator-container">
      <h2>Simple Calculator</h2>
      <div className="calculator">
        <input type="text" value={input} readOnly />
        <div className="buttons">
          {["7", "8", "9", "/", "4", "5", "6", "*", "1", "2", "3", "-", "0", ".", "=", "+"].map((btn) => (
            <button
              key={btn}
              onClick={() =>
                btn === "=" ? handleCalculate() : handleClick(btn)
              }
              className={btn === "=" ? "equals" : ""}
            >
              {btn}
            </button>
          ))}
          <button onClick={handleClear} className="clear">
            C
          </button>
        </div>
      </div>
    </div>
  );
}

export default App;

```
### App.css
```js
body {
  background: linear-gradient(135deg, #2d2d5e, #2E7D32);
  font-family: "Poppins", sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.calculator-container {
  background-color: #ffffff;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
  text-align: center;
  width: 320px;
}

h2 {
  color: #333;
  margin-bottom: 20px;
}

.calculator input {
  width: 100%;
  height: 50px;
  font-size: 20px;
  text-align: right;
  padding: 10px;
  margin-bottom: 15px;
  border: 2px solid #ddd;
  border-radius: 8px;
  outline: none;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  height: 50px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background-color: #221a1a;
  transition: all 0.2s;
}

button:hover {
  background-color: #c8e6c9;
}

.clear {
  grid-column: span 4;
  background-color: #f44336;
  color: #fff;
}

.clear:hover {
  background-color: #d32f2f;
}

.equals {
  background-color: #4CAF50;
  color: #fff;
}

.equals:hover {
  background-color: #388E3C;
}

@media (max-width: 480px) {
  .calculator-container {
    width: 90%;
    padding: 20px;
  }

  input {
    font-size: 18px;
  }

  button {
    font-size: 16px;
  }
}

```
### index.jsx
```js
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```


## OUTPUT
<img width="1905" height="923" alt="Screenshot 2025-10-24 162430" src="https://github.com/user-attachments/assets/6f134aae-5d28-4429-b6e3-7922064a3643" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
