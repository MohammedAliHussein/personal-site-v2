<script>
    import Project from "../components/Project.svelte";
    export let projectData = [];
</script>

<div class="projects">
    {#each projectData as project}
        <Project {...project}/>
    {/each}
</div>

<style>
    .projects {
        height: fit-content;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>