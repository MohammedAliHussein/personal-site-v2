<script>
    import { onMount } from "svelte";
    import TechnologyType from "../components/TechnologyType.svelte";
    import HeaderTitle from "../components/HeaderTitle.svelte";

    let technologies = [
        {
            "type" : "Front End",
            "technology" : [
                "HTML",
                "CSS",
                "JavaScript",
                "Svelte",
                "React",
                "RollupJS"
            ]
        },
        {
            "type" : "Back End",
            "technology" : [
                "NodeJS",
                "Java",
                "Express"
            ]
        },
        {
            "type" : "Testing Framework",
            "technology" : [
                "JUnit",
                "Cypress",
                "Chai"
            ]
        },
        {
            "type" : "Version Control",
            "technology" : [
                "Git",
                "Github"
            ]
        },
        {
            "type" : "Scripting",
            "technology" : [
                "Shell Scripts"
            ]
        }
    ];

    let ready = false;

    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="technologies">
        <HeaderTitle title={"[Technologies]"}/>
        {#each technologies as technology}
            <TechnologyType {...technology}/>
        {/each}
    </div>
{/if}

<style>
    .technologies {
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>