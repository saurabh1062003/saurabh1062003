HTML Template (index.html):
html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Car Price Prediction</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <h1>Car Price Prediction</h1>
    <form action="/predict" method="post">
        <label for="year">Year:</label>
        <input type="number" id="year" name="year" required><br><br>
        <label for="mileage">Mileage (in miles):</label>
        <input type="number" id="mileage" name="mileage" required><br><br>
        <label for="engine_size">Engine Size (in liters):</label>
        <input type="number" id="engine_size" name="engine_size" step="0.1" required><br><br>
        <label for="fuel_type">Fuel Type:</label>
        <select id="fuel_type" name="fuel_type">
            <option value="gas">Gas</option>
            <option value="diesel">Diesel</option>
        </select><br><br>
        <label for="transmission_type">Transmission Type:</label>
        <select id="transmission_type" name="transmission_type">
            <option value="manual">Manual</option>
            <option value="automatic">Automatic</option>
        </select><br><br>
        <label for="cylinders">Cylinders:</label>
        <input type="number" id="cylinders" name="cylinders" required><br><br>
        <input type="submit" value="Predict">
    </form>
    {% if prediction_text %}
    <h2>{{ prediction_text }}</h2>
    {% endif %}
</body>
</html>
4. CSS Styling (style.css):
css
Copy code
body {
    font-family: Arial, sans-serif;
}

form {
    max-width: 400px;
    margin: 0 auto;
}

input[type="number"], select {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
