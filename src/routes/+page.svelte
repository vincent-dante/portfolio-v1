<script>
	import Header from '$lib/components/header.svelte';
	import Projects from '$lib/components/projects.svelte';
</script>

<svelte:head>
	<title>Vincent Dante - Projects</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="py-14 px-4 max-w-6xl mx-auto bg-image">
	<Header />
	<div class="flex w-full items-center justify-center gap-10 mb-14">
		<a href="/" class="text-sky-600">Projects</a>
		<a href="/aboutme">About Me</a>
		<a href="/experience">Experience</a>
	</div>
	<Projects />
</div>
