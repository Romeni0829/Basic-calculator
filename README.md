
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      width: 260px;
    }

    #result {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: center;
      margin-bottom: 20px;
      padding: 5px 0px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 15px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background-color: #e0e0e0;
    }

    button.operator {
      background-color: #0078d7;
      color: white;
    }

    button.equal {
      background-color: #28a745;
      color: white;
      grid-column: span 2;
    }

    button.clear {
      background-color: #dc3545;
      color: white;
      grid-column: span 3;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="result" readonly>
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
      document.getElementById('result').value += value;
    }

    function clearResult() {
      document.getElementById('result').value = '';
    }

    function calculate() {
      try {
        const output = eval(document.getElementById('result').value);
        document.getElementById('result').value = output;
      } catch (e) {
        document.getElementById('result').value = 'Error';
      }
    }
  </script>

</body>
</html>
