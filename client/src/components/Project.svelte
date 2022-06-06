<script>
    import ProjectTitle from "./ProjectTitle.svelte";
    import ProjectDescription from "./ProjectDescription.svelte";
    import ProjectTechnologies from "./ProjectTechnologies.svelte";

    import { fly } from "svelte/transition";
    import { onMount } from "svelte";

    export let title = "title";
    export let description = "description";
    export let technologies = [];
    export let github = "";
    export let link = "";
    export let index = 0;
    export let inProgress = false;

    let ready = false;

    onMount(() => {
        ready = true;
    });

</script>

{#if ready}
    <div class="project" in:fly={{duration: 800, y: -20, delay: (index * 300) + 300}}>
        <ProjectTitle title={title}/>
        <div class="links">
            {#if github !== ""}
                <i title="Open in new tab" class="fa-brands fa-github fa-lg" on:click={window.open(github)}></i>
            {/if}
            {#if link !== ""}
                <i title="Open in new tab" class="fa-solid fa-up-right-from-square fa-lg" on:click={window.open(link)}></i>    
            {/if}
            {#if inProgress}
                <i id="hammer" title="In progress" class="fa-solid fa-hammer fa-fade"></i>
            {/if}
        </div>
        <ProjectDescription description={description}/>
        <ProjectTechnologies technologies={technologies}/>
    </div>
{/if}

<style>
    .project {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        flex-direction: column;
        width: 400px;
        height: 250px;
        filter: drop-shadow(0px 0px 8px rgba(0, 0, 0, 0.25));
        margin: 20px;
        outline: 1px solid rgba(72, 72, 72, 0.1);
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

    .links {
        height: fit-content;
        width: 30%;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        background: none;
    }

    i {
        cursor: pointer;
    }

    #hammer {
        cursor: auto;
    }
</style>