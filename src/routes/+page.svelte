<script>
	import { pokemon } from '../stores/pokestore';
	import PokemanCard from '../components/pokemanCard.svelte';

	let searchTerm = '';
	let filterePokemon = [];

	$: {
		if (searchTerm) {
			filterePokemon = $pokemon.filter((pokeman) =>
				pokeman.name.toLowerCase().includes(searchTerm.toLowerCase())
			);
		} else {
			filterePokemon = [...$pokemon];
		}
	}
</script>

<svelte:head>
	<title>Svelte Kit Pokdex</title>
</svelte:head>

<h1 class="text-4xl text-center my-8 uppercase">Svelte Kit Pokedex</h1>

<input
	type="text"
	class="w-full round-md text-lg p-4 border-2 border-gray-200"
	placeholder="Search Pokemon"
	bind:value={searchTerm}
/>
<div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
	{#each filterePokemon as pokeman}
		<PokemanCard {pokeman} />
	{/each}
</div>

<style>
	h1 {
		color: red;
	}
</style>
