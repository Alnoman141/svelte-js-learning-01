<script>
	// import Variables from './components/Variables.svelte';
	// import Reactivity from './components/Reactivity.svelte';
	// import PropComponent from './components/PropComponent.svelte';
	// import AwaitBlock from './components/AwaitBlock.svelte';
	// import Logic from './components/Logic.svelte';
	// import DomEvents from './components/DomEvents.svelte';
	import Binding from './components/Binding.svelte';
</script>

<main>
	<!-- <Variables /> -->
	<!-- <Reactivity /> -->
	<!-- <PropComponent /> -->
	<!-- <Logic /> -->
	<!-- <AwaitBlock /> -->
	<!-- <DomEvents /> -->
	<Binding />
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