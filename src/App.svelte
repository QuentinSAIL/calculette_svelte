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

<section>
	<div>
		<input type="text" readonly value={numberInput} />
	</div>

	<div>
		<Keypad label="7" onClick={() => addToEquation('7')} />
		<Keypad label="8" onClick={() => addToEquation('8')} />
		<Keypad label="9" onClick={() => addToEquation('9')} />
		<Keypad label="+" onClick={() => addToEquation('+')} />
	</div>
	<div>
		<Keypad label="4" onClick={() => addToEquation('4')} />
		<Keypad label="5" onClick={() => addToEquation('5')} />
		<Keypad label="6" onClick={() => addToEquation('6')} />
		<Keypad label="-" onClick={() => addToEquation('-')} />
	</div>
	<div>
		<Keypad label="1" onClick={() => addToEquation('1')} />
		<Keypad label="2" onClick={() => addToEquation('2')} />
		<Keypad label="3" onClick={() => addToEquation('3')} />
		<Keypad label="*" onClick={() => addToEquation('*')} />
	</div>
	<div>
		<Keypad label="C" onClick={() => clear()} />
		<Keypad label="0" onClick={() => addToEquation('0')} />
		<Keypad label="=" onClick={() => calculate()} />
		<Keypad label="/" onClick={() => addToEquation('/')} />
	</div>
</section>