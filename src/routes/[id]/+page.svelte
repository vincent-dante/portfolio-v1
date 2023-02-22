<script>
	import { page } from '$app/stores';
	import projects from '$lib/data/projects.json';

	const params = $page.params;

	let selectedProject = {
		id: '',
		coverImage: '',
		title: '',
		date: '',
		introduction: '',
		technology: '',
		link: '',
		github: '',
		features: ['']
	};

	const projectFind = projects.find((proj) => proj.id === params.id);
	if (projectFind != undefined) selectedProject = projectFind;
</script>

<svelte:head>
	<title>Vincent Dante - About Me</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="px-4 max-w-6xl mx-auto">
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
					class="w-full h-auto rounded-lg"
					width="900"
					height="600"
				/>
			</picture>
			<h1 class="text-4xl font-bold py-5">{selectedProject.title}</h1>
			<p class="pb-8">Date {selectedProject.date}</p>

			<p>{selectedProject.introduction}</p>

			<h2 class="font-bold pt-5 pb-2">Live preview</h2>
			<a href={selectedProject.link} class="text-sky-500 hover:underline" target="_blank">
				{selectedProject.link}
			</a>

			<h2 class="font-bold pt-5 pb-2">Github</h2>
			<a href={selectedProject.github} class="text-sky-500 hover:underline" target="_blank">
				{selectedProject.github}
			</a>

			<h2 class="font-bold pt-5 pb-2">Tech Stacks</h2>
			<p>{selectedProject.technology}</p>

			<h2 class="font-bold pt-5 pb-2">Features</h2>
			<ul class="list-disc pl-4">
				{#each selectedProject.features as feature}
					<li>{feature}</li>
				{/each}
			</ul>
		{/if}
	</div>
</div>
