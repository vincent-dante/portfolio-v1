<script>
	import { onMount } from 'svelte';
	import projects from '$lib/data/projects.json';
	import { animateElementsOnView } from '$lib/functions/animate.js';

	const project = [...projects]
		.filter((p) => p.enabled)
		.sort((a, b) => {
			return a.order < b.order ? 1 : -1;
		});

	onMount(() => {
		const elementsToTop = document.querySelectorAll('.hidden-element-from-top');
		animateElementsOnView(elementsToTop, 'show-element-from-top');
	});
</script>

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
	{#each project as { id, coverImage, title, logo, projectType }}
		<a href={`/${id}`} class="hidden-element-from-top card">
			<div class="bg-slate-300 group relative overflow-hidden rounded-lg">
				<picture>
					<source srcset={coverImage + '.webp'} type="image/webp" />
					<img src={coverImage + '.jpg'} alt={title} class="w-full " width="400" height="267" />
				</picture>
				<div
					class="absolute inset-0 bg-black opacity-0 group-hover:opacity-25 ease-in-out transition duration-300"
				/>
			</div>
			<div class="flex items-center justify-between pt-3">
				<div class="flex items-center">
					<img src={logo + '.png'} alt={title} width="20" height="20" />
					<div class="text-xl font-bold text-ellipsis whitespace-nowrap overflow-hidden px-2">
						{title}
					</div>
				</div>
				<span
					class="text-xs font-bold uppercase bg-[#F7EFE5] text-[#717171] px-2 py-1 rounded-md whitespace-nowrap"
					>{projectType}</span
				>
			</div>
		</a>
	{/each}
</div>

<style>
	:global(.hidden-element-from-top) {
		opacity: 0;
		transform: translateY(50%);
		transition: all 0.5s;
	}
	:global(.show-element-from-top) {
		opacity: 1 !important;
		transform: translateY(0);
	}
	:global(.card:nth-child(1)) {
		transition-delay: 100ms;
	}
	:global(.card:nth-child(2)) {
		transition-delay: 200ms;
	}
	:global(.card:nth-child(3)) {
		transition-delay: 300ms;
	}
</style>
