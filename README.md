## javascript-basic-calculator

JavaScript Calculator is used to perform mathematical operations like – Addition, Subtraction, Multiplication, Division, etc.
and JavaScript are used to design the JavaScript Calculator. HTML is used to design the basic structure of the calculator. CSS styles are used to apply styles on the calculator and JavaScript is used to add the calculation functionality. Also, Math.js is used to evaluate the calculations.


## overview
HTML Table is used to create a grid structure and <input type=”button”> adds the buttons on the grid.
<input type=”text”> is used to add an input text field to display the expression.
When the user clicks on the button, the button value will display on the input field.
When the equal button ( = ) is clicked, solve() function is called and evaluates the expression, and displays the result on the input text field.
The button “c” is used to clear the text input field. When the button is clicked, the clr() function is called, and it resets the value to empty.
The solve() function uses Math.js evaluate() function to evaluate the mathematical expression.
## screenshot
-desktop view
![](./desktop calculator src.jpg)

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Media Queries
- Javascript
- Events
  
##What I learned
how to use css animation and learned about oninput event use in input to restrict input type number to its maxlength(which not works in input type number).

To see how you can add code snippets, see below:
```html
<!DOCTYPE html>
<html>

<head>
	<title>JavaScript Calculator</title>
	<script src=
"https://cdnjs.cloudflare.com/ajax/libs/mathjs/10.6.4/math.js"
		integrity=
"sha512-BbVEDjbqdN3Eow8+empLMrJlxXRj5nEitiCAK5A1pUr66+jLVejo3PmjIaucRnjlB0P9R3rBUs3g5jXc8ti+fQ=="
		crossorigin="anonymous"
		referrerpolicy="no-referrer"></script>
	<script src=
"https://cdnjs.cloudflare.com/ajax/libs/mathjs/10.6.4/math.min.js"
		integrity=
"sha512-iphNRh6dPbeuPGIrQbCdbBF/qcqadKWLa35YPVfMZMHBSI6PLJh1om2xCTWhpVpmUyb4IvVS9iYnnYMkleVXLA=="
		crossorigin="anonymous"
		referrerpolicy="no-referrer"></script>
```
	
```css
<!-- For styling -->
	<style>
		table {
			border: 1px solid black;
			margin-left: auto;
			margin-right: auto;
		}

		input[type="button"] {
			width: 100%;
			padding: 20px 40px;
			background-color: green;
			color: white;
			font-size: 24px;
			font-weight: bold;
			border: none;
			border-radius: 5px;
		}

		input[type="text"] {
			padding: 20px 30px;
			font-size: 24px;
			font-weight: bold;
			border: none;
			border-radius: 5px;
			border: 2px solid black;
		}
	</style>
```

```
html
</head>
	
<body>
	
	<!-- Use Table to Create Calculator Structure Design -->
	<table id="calcu">
		<tr>
			<td colspan="3"><input type="text" id="result"></td>
			<td><input type="button" value="c" onclick="clr()" /> </td>
		</tr>
		<tr>
			<td><input type="button" value="1" onclick="dis('1')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="2" onclick="dis('2')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="3" onclick="dis('3')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="/" onclick="dis('/')"
						onkeydown="myFunction(event)"> </td>
		</tr>
		<tr>
			<td><input type="button" value="4" onclick="dis('4')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="5" onclick="dis('5')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="6" onclick="dis('6')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="*" onclick="dis('*')"
						onkeydown="myFunction(event)"> </td>
		</tr>
		<tr>
			<td><input type="button" value="7" onclick="dis('7')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="8" onclick="dis('8')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="9" onclick="dis('9')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="-" onclick="dis('-')"
						onkeydown="myFunction(event)"> </td>
		</tr>
		<tr>
			<td><input type="button" value="0" onclick="dis('0')"
						onkeydown="myFunction(event)"> </td>
			<td><input type="button" value="." onclick="dis('.')"
						onkeydown="myFunction(event)"> </td>
			
			<!-- solve function call function solve to evaluate value -->
			<td><input type="button" value="=" onclick="solve()"> </td>

			<td><input type="button" value="+" onclick="dis('+')"
						onkeydown="myFunction(event)"> </td>
		</tr>
	</table>

```javascript
	<script>
		
		// Function that display value
		function dis(val) {
			document.getElementById("result").value += val
		}

		function myFunction(event) {
			if (event.key == '0' || event.key == '1'
				|| event.key == '2' || event.key == '3'
				|| event.key == '4' || event.key == '5'
				|| event.key == '6' || event.key == '7'
				|| event.key == '8' || event.key == '9'
				|| event.key == '+' || event.key == '-'
				|| event.key == '*' || event.key == '/')
				document.getElementById("result").value += event.key;
		}

		var cal = document.getElementById("calcu");
		cal.onkeyup = function (event) {
			if (event.keyCode === 13) {
				console.log("Enter");
				let x = document.getElementById("result").value
				console.log(x);
				solve();
			}
		}

		// Function that evaluates the digit and return result
		function solve() {
			let x = document.getElementById("result").value
			let y = math.evaluate(x)
			document.getElementById("result").value = y
		}

		// Function that clear the display
		function clr() {
			document.getElementById("result").value = ""
		}
	</script>
</body>
```

</html>

