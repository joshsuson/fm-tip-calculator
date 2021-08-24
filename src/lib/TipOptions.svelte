<script>
	const tipOptions = [
		{
			label: '5%',
			decimal: 0.05,
			selected: false
		},
		{
			label: '10%',
			decimal: 0.1,
			selected: false
		},
		{
			label: '15%',
			decimal: 0.15,
			selected: false
		},
		{
			label: '25%',
			decimal: 0.25,
			selected: false
		},
		{
			label: '50%',
			decimal: 0.5,
			selected: false
		}
	];

	export let selected;
	export let tipPercentage;
	let customTip;

	const logTipOption = (option) => {
		selected = option.label;
		tipPercentage = option.decimal;
	};

	const selectCustomTip = () => {
		selected = 'custom-tip';
	};

	$: tipPercentage = customTip / 100;
</script>

<section>
	<h2>Select Tip %</h2>
	<div class="container">
		{#each tipOptions as option}
			<div
				on:click={() => logTipOption(option)}
				class={option.label === selected ? 'selected' : 'tip-option'}
			>
				{option.label}
			</div>
		{/each}
		<input bind:value={customTip} on:focus={selectCustomTip} type="number" placeholder="Custom" />
	</div>
</section>

<style>
	section {
		margin-block: 4rem;
	}
	h2 {
		margin: 0;
		padding: 0;
		margin-bottom: 1rem;
		color: var(--darker-cyan);
		font-size: 2rem;
		font-weight: 400;
	}
	.container {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		gap: 1.5rem;
	}

	.tip-option {
		background: var(--darkest-cyan);
		color: var(--white);
		font-weight: 700;
		font-size: 2.5rem;
		display: grid;
		place-content: center;
		padding: 0.5rem;
		border-radius: 0.5rem;
		cursor: pointer;
	}

	.selected {
		background: var(--light-cyan);
		color: var(--darkest-cyan);
		font-weight: 700;
		font-size: 2.5rem;
		display: grid;
		place-content: center;
		padding: 0.5rem;
		border-radius: 0.5rem;
		cursor: pointer;
	}
	input {
		font-size: 2.25rem;
		padding: 0.5rem;
		border: none;
		background: var(--lighter-cyan);
		font-family: 'Space Mono', monospace;
		border-radius: 5px;
		display: block;
		width: 104px;
		text-align: right;
		font-weight: 700;
		border: 2px solid var(--white);
		color: var(--darkest-cyan);
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

	@media (max-width: 375px) {
		.container {
			grid-template-columns: 1fr 1fr;
		}
	}
</style>
