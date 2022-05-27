<script>
    import { onMount } from "svelte";
    import { fly } from "svelte/transition";

    let ready = false;
    let showingName = false;

    function showName() {
        showingName = true;
    }

    function hideName() {
        showingName = false;
    }

    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="link">
        <i class="fa-regular fa-user" on:mouseover={showName} on:mouseleave={hideName}></i>
        {#if showingName}
            <h5 in:fly={{duration: 500, x: -10}} out:fly={{duration: 500, x: -10}}>Project Portal</h5>
        {/if}
    </div>
{/if}

<style>
    .link {
        position: absolute;
        top: 0;
        left: 0;
        cursor: pointer;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    i {
        margin: 20px;
    }

    h5 {
        font-size: 10px;
        font-weight: 500;
    }
</style>