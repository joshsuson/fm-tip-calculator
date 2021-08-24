<script>
	export let label;
	export let icon;
	export let alt;
	export let value;
	let error = false;

	const checkError = () => {
		if (value < 1) {
			error = true;
		} else {
			error = false;
		}
	};
</script>

<section>
	<label for={label}
		>{label}
		{#if error}
			<span>Can't be zero</span>
		{/if}
	</label>
	<div>
		<input bind:value on:blur={checkError} class:error type="number" name={label} placeholder="0" />
		<img src={icon} {alt} />
	</div>
</section>

<style>
	div {
		position: relative;
	}
	label {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		margin-bottom: 1rem;
		color: var(--darker-cyan);
	}
	span {
		font-size: 1.5rem;
		color: var(--error);
	}
	img {
		position: absolute;
		top: 11px;
		left: 8px;
	}
	input {
		text-align: right;
		height: 5rem;
		font-size: 3rem;
		padding: 1rem;
		border: none;
		background: var(--lighter-cyan);
		font-family: 'Space Mono', monospace;
		border-radius: 5px;
		color: var(--darkest-cyan);
		border: 2px solid var(--white);
	}

	input:focus {
		outline: none;
		border: 2px solid var(--primary-color);
	}

	input[type='number']::-webkit-inner-spin-button,
	input[type='number']::-webkit-outer-spin-button {
		-webkit-appearance: none;
		margin: 0;
		display: none;
	}

	.error {
		border: 2px solid var(--error);
	}
</style>
