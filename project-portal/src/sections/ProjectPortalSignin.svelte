<script>
    import InputField from "../components/InputField.svelte";
    import SubmitButton from "../components/SubmitButton.svelte";
    import Title from "../components/Title.svelte";

    import { onMount } from "svelte";

    let ready = false;

    onMount(() => {
        ready = true;
    })
</script>

{#if ready}
    <div class="project-portal-signin">
        <Title title={"Project Portal"}/>
        <InputField fieldType={"email"} fieldName={"username"}/>
        <InputField fieldType={"password"} fieldName={"password"}/>
        <SubmitButton />
    </div>
{/if}

<style>
    .project-portal-signin {
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>