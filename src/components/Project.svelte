<script>
    import ProjectTitle from "./ProjectTitle.svelte";

    export let title;
    export let description;
    export let techonologies;

</script>

<div class="project">
    <ProjectTitle title={title}/>
    <!-- <ProjectDescription description={description}> -->
    <!-- <ProjectTechnologies techonologies={techonologies}> -->
</div>

<style>

</style>