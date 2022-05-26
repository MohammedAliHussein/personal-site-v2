<script>

	import Header from "./sections/Header.svelte";
	import Projects from "./sections/Projects.svelte";
	import Education from "./sections/Education.svelte";
	import { onMount } from "svelte";
	import axios from "axios";

	let ready = false;
	let projectData = [];
	let educationScrollY = window.scrollY;
	let projectsScrollY = window.scrollY;

	$: showingEducation = educationScrollY >= (window.innerHeight / 3);
	$: showingProjects = projectsScrollY >= (window.innerHeight);

	window.addEventListener("scroll", () => {
		if(!showingProjects) {
			projectsScrollY = window.scrollY;
		}
		if(!showingEducation) {
			educationScrollY = window.scrollY;
		}
	});

	onMount(async () => {
		let bulkData = (await axios.get("http://localhost:3000/api/v1/projects")).data;

		let keys = Object.keys(bulkData);

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
	<!-- <Technologies/> --> 
{/if}
</main>

<style>
	main {
		height: 200vh;
	}
</style>