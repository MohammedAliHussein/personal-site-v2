<script>
    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <button>Submit</button>
{/if}

<style>
    button {
        outline: none;
        background: none;
        border: 1px solid white;
        cursor: pointer;
        padding: 1px 8px;
        margin-top: 15px;
        transition: 0.2s cubic-bezier(0, 0.55, 0.45, 1);
    }

    button:hover {
        background-color: white;
        color: black;  
    }
</style>