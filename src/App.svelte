<script>
	import Header from "./sections/Header.svelte";
	import Education from "./sections/Education.svelte";
	import { onMount } from "svelte";

	let ready = false;
	let scrollY;
	let innerHeight;
	let showingEducation;

	onMount(() => {
		ready = true;
		showingEducation = scrollY >= (innerHeight * 1.2);
	});

</script>

<svelte:window bind:innerHeight={innerHeight} bind:scrollY={scrollY}/>

<main>
{#if ready}
	<Header/>
	{#if scrollY >= innerHeight}
		<Education/>
	{/if}
	<!-- <Projects/>
	<Technologies/> -->
{/if}
</main>

<style>
	main {
		height: 150vh;
	}
</style>