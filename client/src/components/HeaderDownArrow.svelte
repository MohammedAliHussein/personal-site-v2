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
        animation: waitFor 2.8s cubic-bezier(0, 0.55, 0.45, 1) infinite;
    }

    @keyframes waitFor {
        0% {
            opacity: 0;
            transform: translateY(-10px);
        }
        27% {
            opacity: 0;
            transform: translateY(-10px);
        }
        67% {
            opacity: 1;
            transform: translateY(0px);
        }
        100% {
            opacity: 0;
            transform: translateY(0px);
        }
    }
</style>