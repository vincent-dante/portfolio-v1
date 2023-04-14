<script>
	import IconGithub from './icon/github.svelte';
	import IconLinkedin from './icon/linkedin.svelte';
</script>

<div class="flex flex-wrap justify-center mb-3">
	<img
		src="/profile.jpg"
		alt="vincent dante"
		width="112"
		height="112"
		class="w-28 h-28 rounded-full"
	/>
</div>
<div class="text-center mb-10">
	<h1 class="font-bold text-2xl">Vincent Dante</h1>
	<h2 class="text-sm mb-2">Software Engineer | Digital Artist</h2>
	<div class="text-sm flex w-full items-center justify-center gap-1 mb-3">
		<img src="/location-dot-solid.svg" alt="location dot" class="w-3 h-3 inline-block" />
		Manila, Philippines
	</div>
	<div class="text-sm flex w-full items-center justify-center gap-5">
		<a
			href="https://github.com/vincent-dante"
			target="_blank"
			aria-label="Github"
			class="fill-[#353535] hover:fill-gray-600"
		>
			<IconGithub />
		</a>
		<a
			href="https://www.linkedin.com/in/vincent-dante-41358b143/"
			target="_blank"
			aria-label="LinkedIn"
			class="fill-[#353535] hover:fill-gray-600"
		>
			<IconLinkedin />
		</a>
	</div>
</div>
