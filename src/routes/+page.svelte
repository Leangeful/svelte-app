<!-- src\routes\+page.svelte -->
<script lang="ts">
	import { onMount } from 'svelte';
	let lib: typeof import('wasm-lib');

	onMount(async () => {
		lib = await import('wasm-lib');
		await lib.default();
		lib.greet();
	});
</script>

<button on:click={() => lib.greet()}>Greet</button>
