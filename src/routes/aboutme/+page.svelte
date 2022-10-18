<script>
	import Header from '$lib/components/header.svelte';
</script>

<svelte:head>
	<title>Vincent Dante - About Me</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="py-14 px-4 max-w-6xl mx-auto">
	<Header />
	<div class="flex w-full items-center justify-center gap-10 mb-14">
		<a href="/">Projects</a>
		<a href="/aboutme" class="text-sky-500">About Me</a>
		<a href="/experience">Experience</a>
	</div>
	<div class="w-full md:w-5/6 mx-auto">
		<p class="pb-5">
			<span class="text-3xl">Hi!,</span> I'm Vincent and I'm a software engineer, currently reside in
			the Philippines.
		</p>
		<p class="pb-5">
			I build website using the latest technology using HTML5, CSS3, JavaScript ES6, VueJS, React
			and many more. <br /> I enjoy solving complex problem into simple solution.
		</p>
		<p>I love to design and create awesome and interactive website.</p>
	</div>
</div>
