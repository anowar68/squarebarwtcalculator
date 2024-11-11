# squarebarwtcalculator.html
This is square bar weight calculator code for a html website.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Square Bar Weight Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: left;
        }
        h2 {
            margin-top: 20px;
        }
        #calculator-box {
            max-width: 100%;
            margin: 20px auto;
            padding: 10px;
            border: 2px solid rgb(90, 25, 92);
            border-radius: 5px;
            background-color: #f5f7f9;
        }
        #bar-calculator form {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        input[type="text"] {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
            font-size: 18px;
            background-color: white;
        }
        button {
            background-color: #1a2d40;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            font-size: 18px;
        }
        #result {
            margin-top: 20px;
            font-weight: normal;
        }
    </style>
</head>
<body>
   
    <div id="calculator-box">
        <div id="bar-calculator">
            <h2>Square Bar Weight Calculator</h2>
            <form>
                <label for="bar-side">Side Length (mm):</label>
                <input type="text" id="bar-side" name="bar-side" required>
                <label for="bar-length">Bar Length (mm):</label>
                <input type="text" id="bar-length" name="bar-length" required>
                <button id="calculate-button" type="button">Calculate</button>
            </form>
            <div id="result"></div>
        </div>
    </div>
    <script>
        document.getElementById('calculate-button').addEventListener('click', function () {
            const barSide = parseFloat(document.getElementById('bar-side').value);
            const barLength = parseFloat(document.getElementById('bar-length').value);

            if (!isNaN(barSide) && !isNaN(barLength)) {
                const volumeM3 = (Math.pow(barSide / 1000, 2) * (barLength / 1000));
                const densityKgPerM3 = 7850; // Density of steel in Kg/m³
                const weightKg = (volumeM3 * densityKgPerM3).toFixed(2);
                const weightLbs = (weightKg * 2.20462).toFixed(2);

                document.getElementById('result').innerHTML = `1: Weight (Kg): ${weightKg} Kg<br><hr>2: Weight (Lbs): ${weightLbs} Lbs`;
            } else {
                document.getElementById('result').textContent = 'Please enter valid values of the square bar for side length and length.';
            }
        });
    </script>
</body>
</html>

