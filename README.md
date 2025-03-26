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
            background-color: #f0f0f0;
        }
        .calculator {
            background-color: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px #000;
        }
        input[type="text"] {
            width: 100%;
            height: 50px;
            text-align: right;
            font-size: 24px;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
            padding-right: 10px;
        }
        .buttons button {
            width: 60px;
            height: 60px;
            font-size: 22px;
            margin: 5px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .buttons button:hover {
            background-color: #444;
            color: white;
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
        <button onclick="appendValue('/')">/</button>
        <br>
        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="appendValue('*')">*</button>
        <br>
        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('-')">-</button>
        <br>
        <button onclick="appendValue('0')">0</button>
        <button onclick="appendValue('.')">.</button>
        <button onclick="calculate()">=</button>
        <button onclick="appendValue('+')">+</button>
        <br>
        <button onclick="clearResult()" style="width: 252px; background-color: red; color: white;">Clear</button>
    </div>
</div>

<script>
    function appendValue(value) {
        document.getElementById('result').value += value;
    }
    function calculate() {
        try {
            document.getElementById('result').value = eval(document.getElementById('result').value);
        } catch (error) {
            alert('Invalid Expression');
        }
    }
    function clearResult() {
        document.getElementById('result').value = '';
    }
</script>

</body>
</html>
