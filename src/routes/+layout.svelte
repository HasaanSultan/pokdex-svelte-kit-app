<script>
	import Nav from '../components/nav.svelte';
</script>

<Nav />
<h1 class="text-3xl font-bold underline">Hello world!</h1>
<slot />

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
