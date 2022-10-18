<script>
	import projects from '$lib/data/projects.json';
</script>

<div class="grid grid-cols-1 md:grid-cols-3 gap-5">
	{#each projects as { id, coverImage, title }, index}
		<a href={`/${id}`}>
			<picture>
				<source srcset={coverImage + '.webp'} type="image/webp" />
				<img src={coverImage + '.jpg'} alt={title} class="w-full" width="400" height="267" />
			</picture>
		</a>
	{/each}
</div>
