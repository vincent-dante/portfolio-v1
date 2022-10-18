<script>
	import { page } from '$app/stores';
	import Header from '$lib/components/header.svelte';
	import projects from '$lib/data/projects.json';

	const params = $page.params;

	let selectedProject = {
		id: '',
		coverImage: '',
		title: '',
		date: '',
		background: '',
		technology: '',
		link: ''
	};

	const projectFind = projects.find((proj) => proj.id === params.id);
	if (projectFind != undefined) selectedProject = projectFind;
</script>

<svelte:head>
	<title>Vincent Dante - About Me</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="py-14 px-4 max-w-6xl mx-auto">
	<Header />
	<div class="flex w-full items-center justify-center gap-10 mb-14">
		<a href="/" class="text-sky-500">Projects</a>
		<a href="/aboutme">About Me</a>
		<a href="/experience">Experience</a>
	</div>

	<div class="w-full md:w-5/6 mx-auto">
		<div class="pb-5">
			<a href="/" class="inline-block">
				<span class="flex w-full items-center justify-center gap-1">
					<img src="/arrow-left-solid.svg" alt="location dot" class="w-4 h-4 inline-block" />
					Back
				</span>
			</a>
		</div>

		{#if selectedProject.id === ''}
			<h1 class="text-center">No Project Found.</h1>
		{:else}
			<picture>
				<source srcset={selectedProject.coverImage + '.webp'} type="image/webp" />
				<img
					src={selectedProject.coverImage + '.jpg'}
					alt={selectedProject.title}
					class="w-full h-auto"
					width="900"
					height="600"
				/>
			</picture>
			<h1 class="text-4xl font-bold py-5">{selectedProject.title}</h1>
			<p class="pb-8">Date {selectedProject.date}</p>

			<h2 class="font-bold py-5">Background</h2>
			<p>{selectedProject.background}</p>
			<h2 class="font-bold py-5">Technology i use</h2>
			<p>{selectedProject.technology}</p>

			<h2 class="font-bold inline-block my-10">Live website:</h2>
			<a href={selectedProject.link} class="text-sky-500" target="_blank">
				{selectedProject.title}
			</a>
		{/if}
	</div>
</div>
