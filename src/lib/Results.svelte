<script>
	export let tipAmountPerPerson;
	export let totalPerPerson;
	export let reset;
</script>

<section>
	<div>
		<div class="inner-container">
			<div>
				<h2>Tip Amount</h2>
				<h4>/ person</h4>
			</div>
			<div class="price">${tipAmountPerPerson.toFixed(2)}</div>
		</div>
		<div class="inner-container">
			<div>
				<h2>Total</h2>
				<h4>/ person</h4>
			</div>
			<div class="price">${totalPerPerson.toFixed(2)}</div>
		</div>
	</div>
	<div>
		<button disabled={tipAmountPerPerson && totalPerPerson ? false : true} on:click={() => reset()}
			>Reset</button
		>
	</div>
</section>

<style>
	section {
		background: var(--darkest-cyan);
		padding: 4rem;
		border-radius: 1.5rem;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		height: 100%;
	}

	h2 {
		padding: 0;
		margin: 0;
		font-size: 2rem;
		color: var(--white);
	}

	h4 {
		padding: 0;
		margin: 0;
		font-size: 1.5rem;
		color: var(--darker-cyan);
	}

	.price {
		color: var(--primary-color);
		font-size: 4rem;
		font-weight: 700;
	}

	.inner-container {
		display: flex;
		justify-content: space-between;
		margin-bottom: 4rem;
	}

	button {
		background-color: var(--primary-color);
		text-transform: uppercase;
		color: var(--darkest-cyan);
		width: 100%;
		text-align: center;
		font-family: 'Space Mono', monospace;
		font-weight: 700;
		border: none;
		padding: 1rem;
		font-size: 2rem;
		border-radius: 0.5rem;
		cursor: pointer;
	}

	button:disabled {
		background-color: var(--darker-cyan);
	}

	@media (max-width: 375px) {
		section {
			justify-content: inherit;
			height: auto;
		}
	}
</style>
