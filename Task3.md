<!DOCTYPE html>
<html>
<head>
    <title>Temperature Converter</title>
</head>
<body>
    <h1>Temperature Converter</h1>
    
    <input type="number" id="temperatureInput" placeholder="Enter temperature" />
    
    <select id="unitSelect">
        <option value="celsius">Celsius</option>
        <option value="fahrenheit">Fahrenheit</option>
        <option value="kelvin">Kelvin</option>
    </select>
    
    <button onclick="convertTemperature()">Convert</button>
    
    <p id="convertedTemperature"></p>
    
    <script>
        function convertTemperature() {
            const temperature = parseFloat(document.getElementById("temperatureInput").value);
            const selectedUnit = document.getElementById("unitSelect").value;
            let convertedTemperature = 0;
            
            if (selectedUnit === "celsius") {
                convertedTemperature = temperature;
            } else if (selectedUnit === "fahrenheit") {
                convertedTemperature = (temperature * 9/5) + 32;
            } else if (selectedUnit === "kelvin") {
                convertedTemperature = temperature + 273.15;
            }
            
            document.getElementById("convertedTemperature").textContent = 
                `Converted Temperature: ${convertedTemperature.toFixed(2)} ${selectedUnit}`;
        }
    </script>
</body>
</html>
