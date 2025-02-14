<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="keywords" content="Beibei Zhang real estate mortgage calculator">
    <meta name="description" content="Beibei Zhang real estate mortgage calculator">
    <link rel="canonical" href="https://beibeizhang22.github.io/" />
    <title>Loan Payment Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
        }
        .input-group {
            margin-bottom: 15px;
        }
        .input-group label {
            display: block;
            margin-bottom: 5px;
        }
        .input-group input {
           %;
            padding: 8px;
            box-sizing: border-box;
        }
        .result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }
    </style>
</head>
<body>
    <a href="beibiezhang-fixadj.md">Fixed vs Adj Loan</a><a href="beibeizhang-maturity.html">15 vs 30 Years</a>
    <div class="container">
        <h2>Loan Payment Calculator</h2>
        <div class="input-group">
            <label for="principal">Loan Amount (P):</label>
            <input type="number" id="principal" placeholder="Enter loan amount">
        </div>
        <div class="input-group">
            <label for="rate">Annual Interest Rate (r):</label>
            <input type="number" id="rate" step="0.01" placeholder="Enter annual interest rate">
        </div>
        <div class="input-group">
            <label for="periods">Number of Periods (n):</label>
            <input type="number" id="periods" placeholder="Enter number of periods">
        </div>
        <button onclick="calculatePayment()">Calculate Payment</button>
        <div class="result" id="result"></div>
    </div>
 
    <script>
        function calculatePayment() {
            const P = parseFloat(document.getElementById('principal').value);
            const annualRate = parseFloat(document.getElementById('rate').value);
            const n = parseInt(document.getElementById('periods').value);
 
            if (isNaN(P) || isNaN(annualRate) || isNaN(n) || P <= 0 || annualRate <= 0 || n <= 0) {
                document.getElementById('result').innerText = 'Please enter valid values.';
                return;
            }
 
            const r = annualRate / 100 / 12;
            const M = (P * r * Math.pow(1 + r, n)) / (Math.pow(1 + r, n) - 1);
 
            document.getElementById('result').innerText = `Monthly Payment: ${M.toFixed(2)}`;
        }
    </script>
</body>
</html>
