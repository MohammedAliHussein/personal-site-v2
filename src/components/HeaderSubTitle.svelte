<script>
    export let subTitle = "test";

    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <h3>{subTitle}</h3>
{/if}

<style>
    h3 {
        font-size: 16px;
        font-weight: 500;
        margin: 10px;
        animation: slideIn 0.8s cubic-bezier(0, 0.55, 0.45, 1);
    }

    @keyframes slideIn {
        0% {
            opacity: 0;
            transform: translateY(-20px);
            display: none;
        }
        60% { 
            opacity: 0;
            transform: translateY(-20px);
            display: contents;
        }
        100% {
            opacity: 1;
            transform: translateY(0px);
        }
    } 
</style>