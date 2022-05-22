<script>
    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <div class="header-nav">
        <!-- <h5>Projects</h5>
        <h3>|</h3>
        <h5>Education</h5>
        <h3>|</h3>
       <h5>Technologies</h5> -->
    </div>
{/if}

<style>
    .header-nav {
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 14px;
        animation: slideIn 0.5s cubic-bezier(0, 0.55, 0.45, 1) 0.6s;
        opacity: 0;
    }

    h5 {
        margin: 10px;
    }

    @keyframes slideIn {
        0% {
            opacity: 0;
            transform: translateY(-20px);
        }
        100% {
            opacity: 1;
            transform: translateY(0px);
        }
    } 
</style>