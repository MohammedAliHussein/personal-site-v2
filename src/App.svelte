<script>
	import Header from "./sections/Header.svelte";
	import Projects from "./sections/Projects.svelte";
	import Education from "./sections/Education.svelte";
	import { onMount } from "svelte";

	let ready = false;
	let projectData = [];
	let scrollY = window.scrollY;
	$: showingProjects = scrollY >= (window.innerHeight / 3);

	window.addEventListener("scroll", () => {
		// if(!showingProjects) {
			scrollY = window.scrollY;
		// }
		console.log(scrollY);
	})

	onMount(() => {
		projectData = [
			{
				title: "Graph Path Finding Simulation",
				technologies: ["Java", "Gradle", "JUnit", "Git"],
				github: null,
				link: null,
			},
			{
				title: "Single Player Maze Survival Game",
				technologies: ["C", "Make"],
				github: "https://github.com/MohammedAliHussein/Maze-Survival-Game",
				link: null,
			},
			{
				title: "Personal Site V1",
				technologies: ["HTML", "SCSS", "JavaScript", "RollupJS", "Express", "NodeJS", "NPM", "Git"],
				github: "https://github.com/MohammedAliHussein/personal-site-v1",
				link: null,
			},
			{
				title: "Disk Scheduler Simulation",
				technologies: ["Svelte", "CSS", "RollupJS", "Express", "NodeJS", "NPM", "Git"],
				github: "https://github.com/MohammedAliHussein/disk-scheduling-site",
				link: null,
			}
		];
		ready = true;
	});

</script>

<main>
{#if ready}
	<Header/>
	{#if showingProjects}
		<Projects projectData={projectData}/>
	{/if}
	<Education/>
	<!-- <Technologies/> --> 
{/if}
</main>

<style>
	main {
		height: 150vh;
	}
</style>