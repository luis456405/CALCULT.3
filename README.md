<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora</title>
  <style>
    body {
      background: linear-gradient(135deg, #000000 20%, #FFD700 50%, #1E90FF 80%);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      font-family: Arial, sans-serif;
    }

    .calculator {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      text-align: center;
      width: 300px;
    }

    .display {
      width: 100%;
      height: 50px;
      border: 2px solid #ddd;
      border-radius: 5px;
      margin-bottom: 20px;
      font-size: 24px;
      text-align: right;
      padding: 10px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    .buttons button {
      height: 50px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      background: #FFD700;
      color: #000;
      transition: background 0.2s;
    }

    .buttons button:hover {
      background: #1E90FF;
      color: white;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled>
    <div class="buttons">
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('-')">-</button>
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="appendValue('+')">+</button>
      <button onclick="clearDisplay()" style="grid-column: span 2;">C</button>
      <button onclick="deleteLast()" style="grid-column: span 2;">DEL</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function deleteLast() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (error) {
        display.value = 'Erro';
      }
    }
  </script>
</body>
</html>

