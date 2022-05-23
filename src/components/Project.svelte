<script>
    import ProjectTitle from "./ProjectTitle.svelte";
    import ProjectTechnologies from "./ProjectTechnologies.svelte";
import HeaderTitle from "./HeaderTitle.svelte";

    export let title = "title";
    export let description = "description";
    export let technologies = [];
    export let github = "";
    export let link = "";

</script>

<div class="project">
    <ProjectTitle title={title}/>
    <div class="links">
        {#if github !== ""}
            <i class="fa-brands fa-github" on:click={window.open(github, '_blank').focus()}></i>
        {/if}
        {#if link !== null}
            <i class="fa-solid fa-up-right-from-square"></i>    
        {/if}
    </div>
    <!-- <ProjectDescription description={description}> -->
    <ProjectTechnologies technologies={technologies}/>
</div>

<style>
    .project {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        flex-direction: column;
        width: 400px;
        height: 250px;
        background-color:rgb(14, 14, 14);
        filter: drop-shadow(0px 0px 8px rgba(0, 0, 0, 0.1));
        margin: 20px;
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
</style>