<script>
	import src from '../../static/images/logo.svg';
</script>

<div>
	<img {src} alt="Splitter Logo" />
</div>

<style>
	div {
		margin-bottom: 8rem;
	}
	img {
		display: block;
		margin: 0 auto;
	}

	@media (max-width: 375px) {
		div {
			margin: 4rem;
		}
	}
</style>
