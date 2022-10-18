<script>
	import Header from '$lib/components/header.svelte';
</script>

<svelte:head>
	<title>Vincent Dante - Experience</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="py-14 px-4 max-w-6xl mx-auto">
	<Header />
	<div class="flex w-full items-center justify-center gap-10 mb-14">
		<a href="/">Projects</a>
		<a href="/aboutme">About Me</a>
		<a href="/experience" class="text-sky-500">Experience</a>
	</div>
	<div class="flex flex-wrap gap-5 w-full md:w-5/6 mx-auto">
		<div>
			<p class="font-bold pb-2">UBx (Mar 2022 - Present) Software Engineer</p>
			<ul class="pl-5 list-disc">
				<li>Designed and coding website applications primarily using NuxtJS, VueJS, React</li>
				<li>Worked as a team member and communicated with peers and Product Owner</li>
				<li>Worked in mutiple different projects in UBx</li>
			</ul>
		</div>
		<div>
			<p class="font-bold pb-2">Global CIS ltd. (July 2019 - Feb 2021) Software Engineer</p>
			<ul class="pl-5 list-disc">
				<li>
					Designed and coding website applications primarily using Coldfusion, Javascript/JQuery,
					HTML, CSS and Oracle DB
				</li>
				<li>
					Managing, maintaining and developing applications and databases in response to company
					needs
				</li>
				<li>
					Worked as a team member and communicated with senior engineers Monitored web pages and
					sites for continuous improvement
				</li>
				<li>Developed maintenance tools for easier handling of information</li>
			</ul>
		</div>
		<div>
			<p class="font-bold pb-2">Esper Bazaar (Dec 2017 - Oct 2018) I.T (Information Technology)</p>
			<ul class="pl-5 list-disc">
				<li>Maintaining company website.</li>
				<li>Designing Banner, Flyers, Tarpaulin, Bill Board for the company.</li>
				<li>Troubleshooting company computer and software. Adding and Updating products in POS</li>
			</ul>
		</div>
	</div>
</div>
