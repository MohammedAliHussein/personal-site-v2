<script>
	import { onMount } from "svelte";

	import Home from "./pages/Home.svelte";

	let ready = false;

	onMount(() => {
		ready = true;
	});
</script>

<main>
	{#if ready}
		<Home/>
	{/if}
</main>