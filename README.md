# SIP
Sip calculator that can help to calculate future return
<!DOCTYPE html>
<html>
<head>
	<title>SIP Calculator</title>
</head>
<body>
	<h1>SIP Calculator</h1>
	<form>
		<label for="investmentAmount">Investment Amount:</label>
		<input type="number" id="investmentAmount" name="investmentAmount" required><br><br>

		<label for="duration">Duration (in years):</label>
		<input type="number" id="duration" name="duration" required><br><br>

		<label for="interestRate">Expected Annual Interest Rate (%):</label>
		<input type="number" id="interestRate" name="interestRate" required><br><br>

		<button type="button" onclick="calculate()">Calculate</button><br><br>

		<label for="totalAmount">Total Amount:</label>
		<input type="text" id="totalAmount" name="totalAmount" readonly><br><br>

		<label for="totalInterest">Total Interest:</label>
		<input type="text" id="totalInterest" name="totalInterest" readonly><br><br>
	</form>

	<script>
		function calculate() {
			const investmentAmount = document.getElementById("investmentAmount").value;
			const duration = document.getElementById("duration").value;
			const interestRate = document.getElementById("interestRate").value;

			const monthlyInvestment = investmentAmount / (duration * 12);
			const totalAmount = investmentAmount * (1 + ((interestRate/100) / 12)) ** (duration * 12);
			const totalInterest = totalAmount - investmentAmount;

			document.getElementById("totalAmount").value = totalAmount.toFixed(2);
			document.getElementById("totalInterest").value = totalInterest.toFixed(2);
		}
	</script>
</body>
</html>
