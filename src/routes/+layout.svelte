<script>
	import '../app.css';
	import Header from '$lib/components/header.svelte';
	import Footer from '$lib/components/footer.svelte';

	import { page } from '$app/stores';
	let path = '';

	$: path = $page.url.pathname;
</script>

<div class="py-14 px-4 max-w-6xl mx-auto bg-image">
	<Header />
	<div class="flex w-full items-center justify-center gap-10 mb-14">
		<a href="/" class={path === '/' ? 'text-sky-600' : ''}>Projects</a>
		<a href="/aboutme" class={path === '/aboutme' ? 'text-sky-600' : ''}>About Me</a>
		<a href="/experience" class={path === '/experience' ? 'text-sky-600' : ''}>Experience</a>
	</div>
	<slot />
	<Footer />
</div>
