<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unit Converter</title>

    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #3498db; /* Blue background */
            text-align: center;
            margin: 50px;
            color: white; /* White text */
        }

        h2 {
            color: #fff; /* White text */
        }

        label {
            font-size: 16px;
            margin-right: 10px;
            color: #fff; /* White text */
        }

        select, input, button {
            padding: 10px;
            margin-bottom: 10px;
            font-size: 16px;
            border: 1px solid #fff; /* White border */
            border-radius: 5px;
            background-color: #fff; /* White background */
            color: #3498db; /* Blue text */
        }

        button {
            background-color: #3498db; /* Blue background */
            color: white; /* White text */
            cursor: pointer;
        }

        button:hover {
            background-color: #2980b9; /* Slightly darker blue on hover */
        }

        h3 {
            color: #fff; /* White text */
        }

        #resultBox {
            padding: 10px;
            font-size: 18px;
            color: #3498db; /* Blue text */
            border: 1px solid #fff; /* White border */
            border-radius: 5px;
            margin-top: 20px;
            background-color: #fff; /* White background */
        }
    </style>
</head>
<body>

    <h2>Unit Converter</h2>

    <label for="conversionType">Select Conversion Type:</label>
    <select id="conversionType">
        <option value="fahrenheitToCelsius">Fahrenheit to Celsius</option>
        <option value="celsiusToFahrenheit">Celsius to Fahrenheit</option>
        <option value="metersToFeet">Meters to Feet</option>
        <option value="feetToMeters">Feet to Meters</option>
    </select>

    <br>

    <label for="inputValue">Enter Value:</label>
    <input type="number" id="inputValue" step="any">

    <br>

    <button onclick="convert()">Convert</button>

    <div id="resultBox"></div>

    <script>
        function convert() {
            // Get the selected conversion type and input value
            const conversionType = document.getElementById('conversionType').value;
            const inputValue = parseFloat(document.getElementById('inputValue').value);

            // Perform the conversion based on the selected type
            let result = 0;

            switch (conversionType) {
                case 'fahrenheitToCelsius':
                    result = (inputValue - 32) * (5 / 9);
                    break;
                case 'celsiusToFahrenheit':
                    result = (inputValue * 9 / 5) + 32;
                    break;
                case 'metersToFeet':
                    result = inputValue * 3.28084;
                    break;
                case 'feetToMeters':
                    result = inputValue / 3.28084;
                    break;
                default:
                    result = "Invalid conversion type";
            }

            document.getElementById('resultBox').textContent = `Result: ${result.toFixed(2)}`;
        }
    </script>

</body>
</html>
