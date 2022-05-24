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
		if(!showingProjects) {
			scrollY = window.scrollY;
		}
		console.log(scrollY);
	})

	onMount(() => {
		projectData = [
			{
				title: "Graph Path Finding Simulation",
				description: "Path finding simulation implementing all data structures and algorithms manually. Thoroughly tested all classes and algorithms using JUnit. Achieved a final mark of 95%. [Mean mark across all campuses: 58%]",
				technologies: ["Java", "Gradle", "JUnit", "Git"],
				github: "",
				link: "",
			},
			{
				title: "Single Player Maze Survival Game",
				description: "Single player maze traversal game with a basic artifical intelligence enemy. The player traverses the maze with a range of visibility radii for increased difficulty.",
				technologies: ["C", "Make"],
				github: "https://github.com/MohammedAliHussein/Maze-Survival-Game",
				link: "",
			},
			{
				title: "Personal Site V1",
				description: "First iteration of my site. Learned the basics of web development practices, networking mechanisms and languages.",
				technologies: ["HTML", "SCSS", "JavaScript", "RollupJS", "Express", "NodeJS", "NPM", "Git"],
				github: "https://github.com/MohammedAliHussein/personal-site-v1",
				link: "",
			},
			{
				title: "Disk Scheduler Simulation",
				description: "Visual simulation of disk scheduling algorithms with seek time calculations.",
				technologies: ["Svelte", "CSS", "RollupJS", "Express", "NodeJS", "NPM", "Git"],
				github: "https://github.com/MohammedAliHussein/disk-scheduling-site",
				link: "",
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
	<!-- <Education/> -->
	<!-- <Technologies/> --> 
{/if}
</main>

<style>
	main {
		height: 150vh;
	}
</style>