<script>
    import { onMount } from "svelte";

    let ready = false

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <i class="fa-solid fa-arrow-down fa-fade"></i>
{/if}

<style>
    i {
        margin-top: 10px;
        animation: waitFor 2.8s infinite;
    }

    @keyframes waitFor {
        0% {
            opacity: 0;
        }
        27% {
            opacity: 0;
        }
        67% {
            opacity: 1;
        }
        100% {
            opacity: 0;
        }
    }
</style>