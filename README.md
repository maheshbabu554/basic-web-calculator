# basic-web-calculator
i done a project on a  Basic web calculator and i am using a html , css, javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Basic Calculator</title>
    <link rel="stylesheet" href="cal.css" />
</head>

<body>
    <div class="calculator">
        <input type="text" id="display" disabled />

        <div class="buttons">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="deleteLast()">⌫</button>
            <button class="btn" onclick="appendOperator('%')">%</button>
            <button class="btn" onclick="appendOperator('/')">/</button>

            <button class="btn" onclick="appendNumber('7')">7</button>
            <button class="btn" onclick="appendNumber('8')">8</button>
            <button class="btn" onclick="appendNumber('9')">9</button>
            <button class="btn" onclick="appendOperator('*')">*</button>

            <button class="btn" onclick="appendNumber('4')">4</button>
            <button class="btn" onclick="appendNumber('5')">5</button>
            <button class="btn" onclick="appendNumber('6')">6</button>
            <button class="btn" onclick="appendOperator('-')">-</button>

            <button class="btn" onclick="appendNumber('1')">1</button>
            <button class="btn" onclick="appendNumber('2')">2</button>
            <button class="btn" onclick="appendNumber('3')">3</button>
            <button class="btn" onclick="appendOperator('+')">+</button>

            <button class="btn" onclick="appendNumber('0')">0</button>
            <button class="btn" onclick="appendNumber('.')">.</button>
            <button class="btn equal" onclick="calculate()">=</button>
        </div>
    </div>

    <script src="cal.json"></script>
</body>

</html>



body {
    font-family: 'Poppins', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: linear-gradient(135deg, #5d9cec, #4a89dc);
}

.calculator {
    background: #fff;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    padding: 20px;
    width: 300px;
}

#display {
    width: 100%;
    height: 50px;
    border: none;
    background: #f1f3f6;
    text-align: right;
    font-size: 1.5rem;
    padding: 10px;
    border-radius: 10px;
    margin-bottom: 15px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

.btn {
    background: #f1f3f6;
    border: none;
    padding: 15px;
    font-size: 1.2rem;
    border-radius: 10px;
    cursor: pointer;
    transition: 0.2s;
}

.btn:hover {
    background: #dfe3eb;
}

.equal {
    background: #4a89dc;
    color: #fff;
    grid-column: span 2;
}

.equal:hover {
    background: #357bd8;
}


let display = document.getElementById("display");

function appendNumber(number) {
  display.value += number;
}

function appendOperator(operator) {
  display.value += operator;
}

function clearDisplay() {
  display.value = "";
}

function deleteLast() {
  display.value = display.value.slice(0,
    -1);
}

function calculate() {
  try {
    display.value = eval(display.value);
    } catch (error) {
    display.value = "Error";
    }
}
