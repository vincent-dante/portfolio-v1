<script>
	import projects from '$lib/data/projects.json';

	const project = [...projects].sort((a, b) => {
		if (a.date === b.date) {
			return a.id < b.id ? 1 : -1;
		}
		return a.date < b.date ? 1 : -1;
	});
</script>

<div class="grid grid-cols-1 md:grid-cols-3 gap-5">
	{#each project as { id, coverImage, title }}
		<a href={`/${id}`} class="group relative bg-slate-300 overflow-hidden rounded-lg">
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
