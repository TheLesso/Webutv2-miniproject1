<script></script>

<body>
	<section>
		<button class="blue" value="7" on:click>7</button>
		<button class="blue" value="8" on:click>8</button>
		<button class="blue" value="9" on:click>9</button>
		<button value="+" on:click>+</button>

		<button class="blue" value="4" on:click>4</button>
		<button class="blue" value="5" on:click>5</button>
		<button class="blue" value="6" on:click>6</button>
		<button value="-" on:click>-</button>

		<button class="blue" value="1" on:click>1</button>
		<button class="blue" value="2" on:click>2</button>
		<button class="blue" value="3" on:click>3</button>
		<button value="*" on:click>*</button>

		<button value="," on:click>,</button>
		<button class="blue" value="0" on:click>0</button>
		<button value="enter" on:click>=</button>
		<button value="/" on:click>/</button>
		<button value="sin" on:click>SIN</button>
		<button value="cos" on:click>COS</button>
		<button value="tan" on:click>TAN</button>
		<button value="^" on:click>^</button>
		<button value="log" on:click>LOG</button>
		<button value="ln" on:click>LN</button>
		<button value="clear" style="grid-column: span 2;" on:click>CLEAR</button>
	</section>
</body>

<style lang="scss">
	/*centerar och bestämmer utseende för miniräknaren */
	body {
		max-height: 12rem;
		width: min(100% - 2rem, 800px);
		margin-left: auto;
		margin-right: auto;
		margin-top: 2rem;
		background-color: black;

		button {
			height: 12rem;
			border-radius: 8px;
			color: rgb(70, 198, 240);
			background-color: white;
			font-size: 5rem;
			&:active {
				background-color: rgb(173, 173, 173);
			}
			&.blue {
				color: black;
			}
		}

		section {
			display: grid;
			grid-template-columns: repeat(4, 1fr);
			gap: 0.2rem;
		}
	}

	@media only screen and (max-width: 500px) {
		button {
			max-height: 8rem;
			font-size: 3.5rem;
		}
	}
</style>
