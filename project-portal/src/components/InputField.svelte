<script>
    import { onMount } from "svelte";

    export let fieldType = "text";
    export let fieldName = "field";

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <input type={fieldType} placeholder={fieldName}>
{/if}

<style>
    input {
        outline: none;
        border: 1px solid rgba(255, 255, 255, 0.091);
        text-align: center;
        margin-top: 10px;
        padding: 3px 13px;
        transition: 0.2s cubic-bezier(0, 0.55, 0.45, 1);
    }

    input:focus {
        border: 1px solid rgba(255, 255, 255, 0.25);
    }
</style>