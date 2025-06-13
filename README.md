<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Calculator</title>
  <style>
    body {
      background-color: #f0f4f8;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      background: #ffffff;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      width: 300px;
    }

    #result {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 10px;
      margin-bottom: 20px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 20px;
      font-size: 18px;
      border: none;
      border-radius: 10px;
      background-color: #007BFF;
      color: white;
      cursor: pointer;
      transition: background 0.2s ease;
    }

    button:hover {
      background-color: #0056b3;
    }

    .operator {
      background-color: #28a745;
    }

    .clear {
      background-color: #dc3545;
    }

    .equal {
      background-color: #ffc107;
      color: black;
      grid-column: span 2;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="result" disabled />
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
      <button class="equal" onclick="calculate()">=</button>
      <button class="operator" onclick="appendValue('+')">+</button>

      <button class="clear" onclick="clearResult()">C</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById("result").value += value;
    }

    function clearResult() {
      document.getElementById("result").value = "";
    }

    function calculate() {
      try {
        const result = eval(document.getElementById("result").value);
        document.getElementById("result").value = result;
      } catch (error) {
        document.getElementById("result").value = "Error";
      }
    }
  </script>

</body>
</html>
