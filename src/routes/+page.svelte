<script>
	import Display from '$lib/components/Display.svelte';
	import Keyboard from '$lib/components/Keyboard.svelte';

	let displayValue = '';
	let memory = 0;
	let arithmetic = null;
	let hasArithmetic;
	let hasComma = false;

	function handleClick(e) {
		if (e.target.value >= 0 && e.target.value < 10) {
			if (hasArithmetic) {
				displayValue = '';
				hasArithmetic = false;
			}
			displayValue += e.target.value;
		}

		if (
			e.target.value === '+' ||
			e.target.value === '-' ||
			e.target.value === '*' ||
			e.target.value === '/' ||
			e.target.value === '^' ||
			e.target.value === 'sin' ||
			e.target.value === 'cos' ||
			e.target.value === 'tan' ||
			e.target.value === 'log' ||
			e.target.value === 'ln'
		) {
			memory = displayValue;
			displayValue = '';
			hasArithmetic = true;
			hasComma = false;
			arithmetic = e.target.value;
			displayValue = e.target.value;
		}

		if (e.target.value === 'clear') {
			clear();
		}

		if (e.target.value === ',') {
			addComma();
		}

		if (e.target.value === 'enter') {
			displayValue = calculate();
		}
	}

	function clear() {
		displayValue = '';
		memory = 0;
		hasComma = false;
		hasArithmetic = false;
	}

	function addComma() {
		if (hasComma == false) {
			displayValue += '.';
			hasComma = true;
		}
	}

	function calculate() {
		if (arithmetic === '+') {
			return Number(memory) + Number(displayValue);
		}
		if (arithmetic === '/') {
			return Number(memory) / Number(displayValue);
		}
		if (arithmetic === '*') {
			return Number(memory) * Number(displayValue);
		}
		if (arithmetic === '-') {
			return Number(memory) - Number(displayValue);
		}
		if (arithmetic === '^') {
			return Math.pow(memory, displayValue);
		}
		if (arithmetic === 'SIN') {
			return Math.sin(displayValue);
		}
		if (arithmetic === 'COS') {
			return Math.cos(displayValue);
		}
		if (arithmetic === 'TAN') {
			return Math.tan(displayValue);
		}
		if (arithmetic === 'LOG') {
			return Math.log10(displayValue);
		}
		if (arithmetic === 'LN') {
			return Math.log(displayValue);
		}
	}
</script>

<Display display={displayValue} />
<Keyboard on:click={handleClick} />

