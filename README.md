<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 50px;
        }
        .container {
            max-width: 400px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input, button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            font-size: 16px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Age Calculator</h1>
        <label for="dob">Enter Date of Birth:</label>
        <input type="date" id="dob">
        <button onclick="calculateAge()">Calculate Age</button>
        <h2 id="result"></h2>
    </div>

    <script>
        function calculateAge() {
            const dobInput = document.getElementById('dob').value;
            if (!dobInput) {
                alert("Please enter your date of birth");
                return;
            }

            const dob = new Date(dobInput);
            const today = new Date();

            let age = today.getFullYear() - dob.getFullYear();
            const monthDifference = today.getMonth() - dob.getMonth();
            const dayDifference = today.getDate() - dob.getDate();

            // Adjust age if the current month and day is before the birth month and day
            if (monthDifference < 0 || (monthDifference === 0 && dayDifference < 0)) {
                age--;
            }

            document.getElementById('result').textContent = Your age is: ${age} years;
        }
    </script>
</body>
</html>
