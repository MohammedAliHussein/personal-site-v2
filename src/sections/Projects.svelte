<script>
    import Project from "../components/Project.svelte";
    import HeaderTitle from "../components/HeaderTitle.svelte";

    export let projectData = [];
</script>

<div class="projects-section">
    <HeaderTitle title={"[Projects]"}/>
    <div class="projects">
        {#each projectData as project}
            <Project {...project}/>
        {/each}
    </div>
</div>

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