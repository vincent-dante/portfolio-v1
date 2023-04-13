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

<div class="grid grid-cols-1 md:grid-cols-3 gap-5">
	{#each project as { id, coverImage, title }}
		<a
			href={`/${id}`}
			class="group relative bg-slate-300 overflow-hidden rounded-lg hidden-element-from-top card"
		>
			<picture>
				<source srcset={coverImage + '.webp'} type="image/webp" />
				<img src={coverImage + '.jpg'} alt={title} class="w-full " width="400" height="267" />
			</picture>
			<div
				class="absolute inset-0 bg-black opacity-0 group-hover:opacity-25 ease-in-out transition duration-300"
			/>
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
