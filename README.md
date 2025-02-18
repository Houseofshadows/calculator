# calculator
basic calculator created with html, css and javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        .calculator {
            width: 300px;
            margin: 50px auto;
            background: #f4f4f4;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        #display {
            width: 100%;
            height: 40px;
            margin-bottom: 10px;
            padding: 5px;
            font-size: 20px;
            text-align: right;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 5px;
        }

        button {
            padding: 15px;
            font-size: 18px;
            border: none;
            background: #fff;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background: #eee;
        }

        .operator {
            background: #ff9500;
            color: white;
        }

        .operator:hover {
            background: #db8000;
        }

        .equals {
            background: #2ecc71;
            color: white;
        }

        .equals:hover {
            background: #27ae60;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('/')" class="operator">/</button>
            <button onclick="appendToDisplay('*')" class="operator">×</button>
            <button onclick="backspace()">⌫</button>
            
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('-')" class="operator">-</button>
            
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('+')" class="operator">+</button>
            
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="calculate()" class="equals">=</button>
            
            <button onclick="appendToDisplay('0')" style="grid-column: span 2;">0</button>
            <button onclick="appendToDisplay('.')">.</button>
        </div>
    </div>

    <script>
        let display = document.getElementById('display');

        function appendToDisplay(value) {
            display.value += value;
        }

        function clearDisplay() {
            display.value = '';
        }

        function calculate() {
            try {
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }

        function backspace() {
            display.value = display.value.slice(0, -1);
        }
    </script>
</body>
</html>

