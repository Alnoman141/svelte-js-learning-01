<script>
	import Variables from './components/Variables.svelte';
	import Reactivity from './components/Reactivity.svelte';
</script>

<main>
	<!-- <Variables /> -->
	<Reactivity />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 600px;
		margin: 0 auto;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>