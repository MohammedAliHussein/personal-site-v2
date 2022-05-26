<script>
    import { onMount } from "svelte";
    import { fly } from "svelte/transition";
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
        <div class="technology-type-list">
            {#each technology as tool}
                <h4 in:fly={{duration: 800, y: -20, delay: 800}}>{tool}</h4>
            {/each}
        </div>
    </div>
{/if}

<style>
    .technology-type {
        width: 100%;
        height: fit-content;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .technology-type-list {
        width: fit-content;
        height: fit-content;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 20px;
    }

    h4 {
        background: none;
        font-weight: 400;
        font-size: 13px;
        line-height: 25px;
        margin: 0px 10px;
    }

</style>