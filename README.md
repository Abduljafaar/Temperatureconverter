<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        body {
            background-color: #3498db;
            color: #fff;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        h1 {
            color: #ecf0f1;
        }
        .container {
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 20px;
            margin: 20px auto;
            width: 300px;
        }
        input[type="number"] {
            padding: 5px;
            width: 100%;
            border: none;
            border-radius: 5px;
        }
        select, button {
            padding: 5px;
            width: 100%;
            border: none;
            border-radius: 5px;
            background-color: #2ecc71;
            color: #fff;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>Temperature Converter</h1>
    <div class="container">
        <input type="number" id="temperature" placeholder="Enter temperature">
        <select id="fromUnit">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
        </select>
        <button onclick="convertTemperature()">Convert</button>
        <p id="result"></p>
    </div>

    <script>
        function convertTemperature() {
            const temperature = parseFloat(document.getElementById("temperature").value);
            const fromUnit = document.getElementById("fromUnit").value;
            const toUnit = fromUnit === "celsius" ? "fahrenheit" : "celsius";
            let result;

            if (fromUnit === "celsius") {
                result = (temperature * 9/5) + 32;
            } else {
                result = (temperature - 32) * 5/9;
            }

            document.getElementById("result").textContent = `${temperature} ${fromUnit} is equal to ${result.toFixed(2)} ${toUnit}`;
        }
    </script>
</body>
</html>
