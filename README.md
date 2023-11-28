<!DOCTYPE html>
<html lang="pt-br">

<head>
	<title>Anne's Calculator</title>
	<meta charset="UTF-8">
	<style>
		* {
			box-sizing: border-box;
			transition: .4s;
			align-items: center;
			
		}

		body {
			font-family: Arial, Helvetica, sans-serif;
			font-weight: bold;
			margin: 0;
			padding: 0;
			width: 100%;
			height: 100%;
			background-color: #171717;
			font-size: 60px;
		}

		.container {
			width: 500px;
			height: 400px;
			margin: 30px auto;
			position: inherit;
		}

		.display {
			background-color: hsla(0, 100%, 99%, 0.722);
			padding: 50px;
			border: 40px solid #9d12cf;
			border-radius: 10px 10px 0 0
		}

		.buttons {
			background-color: #9d12cf;
			padding: 20px;
			align-items: center;
			text-align: center;
			border-radius: 0 0 10px 10px;
		}

		button {
			width: 100px;
			height: 50px;
			margin: 10px;
			cursor: pointer;
			color: #000;
			background-color: #ffffffa4;
			border: transparent;
			font-weight: bolder;
			font-size: 22px;
			border-radius: 5px;
		}

		button:hover {
			transition: .5s;
			background-color: #ffffff;
		}

		span {
			font-size: 20px;
		}
	</style>
</head>

<body>
	<div class="container">
		<div class="header">
		</div>
		<div class="display">
			<span id="id01"></span>
			<span id="id02"></span>
			<span id="id03"></span>
			<span id="id04"></span>
		</div>
		<div class="buttons">
			<button onclick="location.reload();">C</button>
			<button onclick="clicouOperador('+')">+</button>
			<button onclick="clicouOperador('-')">-</button>
			<br>
			<button onclick="clicouNumero(1)">1</button>
			<button onclick="clicouNumero(2)">2</button>
			<button onclick="clicouNumero(3)">3</button>
			<br>
			<button onclick="clicouNumero(4)">4</button>
			<button onclick="clicouNumero(5)">5</button>
			<button onclick="clicouNumero(6)">6</button>
			<br>
			<button onclick="clicouNumero(7)">7</button>
			<button onclick="clicouNumero(8)">8</button>
			<button onclick="clicouNumero(9)">9</button>
			<br>
			<button onclick="window.close();">Fechar</button>
			<button onclick="clicouNumero(0)">0</button>
			<button onclick="resultado()">=</button>
		</div>
	</div>
	<script>
		var estado = "id01"
		function clicouNumero(numero) {
			const element = document.getElementById(estado);
			element.innerHTML += numero;
		}
		function clicouOperador(operador) {
			const element = document.getElementById("id02");
			element.innerHTML = operador;
			estado = "id03"
		}
		function resultado() {
			var expressao = "";
			expressao += document.getElementById("id01").innerHTML;
			expressao += document.getElementById("id02").innerHTML;
			expressao += document.getElementById("id03").innerHTML;

			if (expressao === "" || expressao === "+" || expressao === "-" || expressao === "/" || expressao === "*") {

				const element = document.getElementById("id04");
				element.innerHTML = "Expressão inválida";
				return 0;
			}

			const element = document.getElementById("id04");
			element.innerHTML = " = " + eval(expressao);
		}

	</script>
</body>

</html>
