<script>
    import { onMount } from "svelte";
    import HeaderSubTitle from "./HeaderSubTitle.svelte";

    export let type = "";
    export let technology = [];

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <div class="technology-type">
        <HeaderSubTitle subTitle={type} />
        {#each technology as tool}
            <h4>{tool}</h4>
        {/each}
    </div>
{/if}

<style>

</style>