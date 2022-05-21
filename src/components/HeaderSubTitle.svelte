<script>
    export let subTitle;

    import { fly } from "svelte/transition";
    import { circOut } from "svelte/easing";
    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <h3 in:fly={{duration: 500, y: -20, easing: circOut, delay: 300}}>{subTitle}</h3>
{/if}

<style>
    h3 {
        font-size: 16px;
        font-weight: 500;
        margin: 10px;
    }
</style>