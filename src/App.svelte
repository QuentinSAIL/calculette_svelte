<script>
	import Keypad from './components/Keypad.svelte';

	let numberInput = "";

	function addToEquation(value) {
		numberInput += value;
	}

	function clear() {
		numberInput = "";
	}

	function calculate() {
		try {
			numberInput = eval(numberInput).toString();
		} catch (e) {
			numberInput = "Error";
		}
	}
</script>

<section class="calculator">
	<div class="display">
		<input type="text" readonly value={numberInput} />
	</div>

	<div class="keypad">
		<Keypad label="C" onClick={() => clear()} btnClass="grey very-long" />
		<Keypad label="/" onClick={() => addToEquation('/')} btnClass="orange" />

		<Keypad label="7" onClick={() => addToEquation('7')} />
		<Keypad label="8" onClick={() => addToEquation('8')} />
		<Keypad label="9" onClick={() => addToEquation('9')} />
		<Keypad label="*" onClick={() => addToEquation('*')} btnClass="orange" />

		<Keypad label="4" onClick={() => addToEquation('4')} />
		<Keypad label="5" onClick={() => addToEquation('5')} />
		<Keypad label="6" onClick={() => addToEquation('6')} />
		<Keypad label="-" onClick={() => addToEquation('-')} btnClass="orange" />


		<Keypad label="1" onClick={() => addToEquation('1')} />
		<Keypad label="2" onClick={() => addToEquation('2')} />
		<Keypad label="3" onClick={() => addToEquation('3')} />
		<Keypad label="+" onClick={() => addToEquation('+')} btnClass="orange" />

		<Keypad label="0" onClick={() => addToEquation('0')} />
		<Keypad label="," onClick={() => addToEquation('.')} btnClass="long" />
		<Keypad label="=" onClick={() => calculate()} btnClass="orange" />
	</div>
</section>

<style>
	.calculator {
		width: 240px;
		margin: 50px auto;
		background-color: #333;
		border-radius: 12px;
		padding: 20px;
	}

	input {
		width: 100%;
		height: 60px;
		border: none;
		background-color: #555;
		color: white;
		font-size: 30px;
		padding: 10px;
		border-radius: 4px;
		text-align: right;
	}

	.keypad {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 5px;
	}
</style>
