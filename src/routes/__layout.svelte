<script>
	import '../global.css';
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>
<main>
	<slot />
</main>

<style>
	:global(body) {
		background-color: var(--light-cyan);
	}

	main {
		display: grid;
		place-content: center;
		height: 100vh;
	}

	@media (max-width: 375px) {
		main {
			display: block;
			height: auto;
		}
	}
</style>
