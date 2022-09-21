<script>
	export let display = "";
</script>

<input type="text"disabled="disabled" bind:value={display}/>

<style lang="scss">
	input {
		width: min(100%);
		font-size: 5rem;
		margin-bottom: 10px;
		background-color: black;
		color: green;
		text-align: right;
		padding: 10px 4px 10px 4px;
		font-family: lcd;
		border: 1px solid yellow;
		border-radius: 8px;
	}
</style>
