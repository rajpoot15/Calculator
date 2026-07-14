# Calculator

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Calculator</title>
  <style>
    /* CSS STYLING */
    body { 
      background-color: #121212; 
      display: flex; 
      justify-content: center; 
      align-items: center; 
      height: 100vh; 
      margin: 0;
      font-family: Arial, sans-serif;
    }
    .calculator { 
      background: #1e1e1e; 
      padding: 20px; 
      border-radius: 15px; 
      box-shadow: 0px 4px 10px rgba(0,0,0,0.3);
    }
    #display { 
      width: 100%; 
      height: 50px; 
      margin-bottom: 15px; 
      text-align: right; 
      background-color: #2d2d2d;
      border: none;
      color: #fff;
      font-size: 1.5rem;
      padding: 5px 10px;
      box-sizing: border-box;
      border-radius: 5px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button { 
      width: 60px; 
      height: 60px; 
      cursor: pointer; 
      border: none;
      border-radius: 5px;
      font-size: 1.2rem;
      background-color: #3d3d3d;
      color: #fff;
    }
    button.operator {
      background-color: #ff9f0a;
    }
    button.clear {
      background-color: #a5a5a5;
      color: #000;
    }
  </style>
</head>
<body>

  <!-- HTML STRUCTURE -->
  <div class="calculator">
    <input type="text" id="display" readonly>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button class="operator" onclick="appendToDisplay('/')">/</button>
      <button class="operator" onclick="appendToDisplay('*')">*</button>
      <button class="operator" onclick="appendToDisplay('-')">-</button>
      
      <button onclick="appendToDisplay('7')">7</button>
      <button onclick="appendToDisplay('8')">8</button>
      <button onclick="appendToDisplay('9')">9</button>
      <button class="operator" onclick="appendToDisplay('+')">+</button>
      
      <button onclick="appendToDisplay('4')">4</button>
      <button onclick="appendToDisplay('5')">5</button>
      <button onclick="appendToDisplay('6')">6</button>
      <button class="operator" onclick="calculate()">=</button>
      
      <button onclick="appendToDisplay('1')">1</button>
      <button onclick="appendToDisplay('2')">2</button>
      <button onclick="appendToDisplay('3')">3</button>
      <button onclick="appendToDisplay('0')">0</button>
    </div>
  </div>

  <!-- JAVASCRIPT LOGIC -->
  <script>
    const display = document.getElementById('display');

    function appendToDisplay(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function calculate() {
      try {
        // Simple logic evaluation
        display.value = eval(display.value);
      } catch (error) {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
