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
    h3 {
        font-size: 16px;
        font-weight: 500;
        margin: 10px;
        background: none;
    }
</style>
