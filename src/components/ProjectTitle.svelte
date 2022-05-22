<script>
    import { onMount } from "svelte";

    export let title = "";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <h3>{title}</h3>
{/if}

<style>

</style>
