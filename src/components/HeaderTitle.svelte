<script>
    export let title = "ayo?";

    import { fly } from "svelte/transition";
    import { circOut } from "svelte/easing";
    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <h1 in:fly={{duration: 500, y: -20, easing: circOut}}>{title}</h1>
{/if}

<style>
    h1 {
        font-size: 32px;
        font-weight: 700;
    }
</style>