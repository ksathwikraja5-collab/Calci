<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f4f4f9;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }
    .display {
      width: 100%;
      height: 50px;
      margin-bottom: 15px;
      text-align: right;
      font-size: 1.5rem;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      background: #f9f9f9;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 70px);
      gap: 10px;
    }
    button {
      height: 50px;
      font-size: 1.2rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #007bff;
      color: white;
      transition: background 0.3s;
    }
    button:hover {
      background: #0056b3;
    }
    .operator {
      background: #28a745;
    }
    .operator:hover {
      background: #1e7e34;
    }
    .clear {
      background: #dc3545;
    }
    .clear:hover {
      background: #b21f2d;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" class="display" disabled>
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button class="operator" onclick="appendValue('/')">÷</button>
      
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button class="operator" onclick="appendValue('*')">×</button>
      
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button class="operator" onclick="appendValue('-')">−</button>
      
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()">=</button>
      <button class="operator" onclick="appendValue('+')">+</button>
      
      <button class="clear" style="grid-column: span 4;" onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    let display = document.getElementById("display");

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = "";
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
</body>
</html>
