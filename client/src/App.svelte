<script>
	import Header from "./sections/Header.svelte";
	import Education from "./sections/Education.svelte";
	import Projects from "./sections/Projects.svelte";
	import Technologies from "./sections/Technologies.svelte";

	import { onMount } from "svelte";
	import axios from "axios";

	let ready = false;
	let projectData = [];
	let educationScrollY = window.scrollY;
	let projectsScrollY = window.scrollY;
	let technologiesScrollY = window.scrollY;

	$: showingEducation = educationScrollY >= (window.innerHeight / 3);
	$: showingProjects = projectsScrollY >= (window.innerHeight);
	$: showingTechnologies = technologiesScrollY >= (window.innerHeight * 1.9);

	window.addEventListener("scroll", () => {
		if(!showingProjects) {
			projectsScrollY = window.scrollY;
		}
		if(!showingEducation) {
			educationScrollY = window.scrollY;
		}
		if(!showingTechnologies) {
			technologiesScrollY = window.scrollY;
		}
	});

	onMount(async () => {
		const bulkData = (await axios.get("http://localhost:3000/api/v1/projects")).data;

		const keys = Object.keys(bulkData);

		keys.forEach((key) => {
			projectData.push(bulkData[key].project);
		});

		ready = true;
	});

</script>

<main>
{#if ready}
	<Header/>
	{#if showingEducation}
		<Education/>
	{/if}
	{#if showingProjects}
		<Projects projectData={projectData}/>
	{/if}
	{#if showingTechnologies}
		<Technologies/> 
	{/if}
{/if}
</main>

<style>
	main {
		height: 320vh;
	}
</style>