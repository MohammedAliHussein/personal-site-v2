<script>
    import { onMount } from "svelte";

    export let technologies = [];

    let ready = false;

    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="technologies">
        {#each technologies as technology}
            <h4>{technology}</h4>
        {/each}
    </div>
{/if}

<style>
    .technologies {
        width: 75%;
        height: fit-content;
        display: flex;
        flex-wrap: wrap;
        height: fit-content;
        justify-content: space-evenly;
        align-items: center;
        background: none;
    }

    h4 {
        background: none;
        font-weight: 400;
        font-size: 12px;
        line-height: 25px;
        margin-right: 10px;
    }

</style>