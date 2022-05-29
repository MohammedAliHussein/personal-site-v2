<script>
	import ProjectPortal from "./sections/ProjectPortal.svelte";
	import ProjectPortalSignin from "./sections/ProjectPortalSignin.svelte";

	import { onMount } from "svelte";

	let authenticated = false;

	let ready = false;
	
	onMount(() => {
		ready = true;
	});
</script>

<main>
	{#if ready}
		{#if authenticated}
			<ProjectPortal />
		{:else}
			<ProjectPortalSignin />
		{/if}
	{/if}	
</main>

<style>
</style>
