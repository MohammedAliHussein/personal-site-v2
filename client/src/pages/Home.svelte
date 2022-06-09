<script>
	import Header from "../sections/Header.svelte";
	import Education from "../sections/Education.svelte";
	import Projects from "../sections/Projects.svelte";
	import Technologies from "../sections/Technologies.svelte";

	import { onMount } from "svelte";
	import axios from "axios";

	let ready = false;
	let projectData = [];
	let educationScrollY = window.scrollY;
	let projectsScrollY = window.scrollY;
	let technologiesScrollY = window.scrollY;

	$: showingEducation = educationScrollY >= (window.innerHeight / 3);
	$: showingProjects = projectsScrollY >= (window.innerHeight);
	$: showingTechnologies = technologiesScrollY >= (window.innerHeight * 1.7);

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
		const bulkData = (await axios.get("https://localhost:443/api/v1/projects")).data;

		const keys = Object.keys(bulkData);

		keys.forEach((key) => {
			projectData.push(bulkData[key].project);
		});

		ready = true;
	});
</script>

{#if ready}
	<main>
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
	</main>
{/if}

<style>
	main {
		height: 250vh;
	}
</style>