<script>
	import Input from '$lib/Input.svelte';
	import Results from '$lib/Results.svelte';
	import TipOptions from '$lib/TipOptions.svelte';
	import dollarSign from '../../static/images/icon-dollar.svg';
	import person from '../../static/images/icon-person.svg';

	let tipAmountPerPerson = 0.0;
	let totalPerPerson = 0.0;
	let bill = null;
	let numberOfPeople = null;
	let tipPercentage = 0.0;
	let selected;

	const reset = () => {
		tipAmountPerPerson = 0.0;
		totalPerPerson = 0.0;
		bill = null;
		numberOfPeople = null;
		tipPercentage = null;
		selected = null;
	};

	$: if (bill && numberOfPeople) {
		let billWithTip = bill + bill * tipPercentage;
		tipAmountPerPerson = (bill * tipPercentage) / numberOfPeople;
		totalPerPerson = billWithTip / numberOfPeople;
	}
</script>

<section>
	<div>
		<Input bind:value={bill} label="Bill" icon={dollarSign} alt="Dollar Sign Icon" />
		<TipOptions bind:selected bind:tipPercentage />
		<Input bind:value={numberOfPeople} label="Number of People" icon={person} alt="Person Icon" />
	</div>
	<div>
		<Results {reset} {tipAmountPerPerson} {totalPerPerson} />
	</div>
</section>

<style>
	section {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 4rem;
	}

	@media (max-width: 375px) {
		section {
			grid-template-columns: 1fr;
			gap: 4rem;
		}
	}
</style>
