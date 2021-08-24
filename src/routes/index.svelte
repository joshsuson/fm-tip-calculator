<script>
	import Logo from '$lib/Logo.svelte';
	import Calculator from '$lib/Calculator.svelte';
</script>

<section>
	<Logo />
	<div>
		<Calculator />
	</div>
</section>

<style>
	div {
		background-color: var(--white);
		padding: 4rem;
		border-radius: 2rem;
		max-width: 1000px;
	}

	@media (max-width: 375px) {
		div {
			border-radius: 2rem 2rem 0 0;
		}
	}
</style>
