<script>
    import Project from "../components/Project.svelte";
    import HeaderTitle from "../components/HeaderTitle.svelte";
    import { onMount } from "svelte";

    export let projectData = [];

    let ready = false;

    function resize(ready) {
        setTimeout(() => {
            if(ready) {
                console.log(document.querySelector(".projects-section").offsetHeight);
                document.querySelector("main").style.height = `${(document.querySelector(".projects-section").offsetHeight / 10) + 250}vh`; 
            }
        }, 100);
    }

    $: resize(ready);

    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="projects-section">
        <HeaderTitle title={"[Projects]"}/>
        <div class="projects">
            {#each projectData as project, i}
                {#if !project.hidden}
                    <Project {...project} index={i}/>
                {/if}
            {/each}
        </div>
    </div>
{/if}

<svelte:window on:resize={() => { resize(ready) }} />

<style>
    .projects-section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
    }

    .projects {
        height: fit-content;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        margin: 20px;
    }
</style>