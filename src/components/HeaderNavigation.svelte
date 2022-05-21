<script>
    import { fly } from "svelte/transition";
    import { circOut } from "svelte/easing";
    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>


{#if ready}
    <div class="header-nav" in:fly={{duration: 500, y: -20, easing: circOut, delay: 600}}>
        <h5>Projects</h5>
        <h3>|</h3>
        <h5>Education</h5>
        <!-- <h3>|</h3> -->
        <!-- <h5>Technologies</h5> -->
    </div>
{/if}

<style>
    .header-nav {
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 14px;
    }

    h5 {
        margin: 10px;
    }
</style>