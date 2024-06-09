<script>
	import Swal from 'sweetalert2';

	function sendEmail(e) {
		e.preventDefault();

		const form = document.getElementById('form');
		const formData = new FormData(form);
		const object = Object.fromEntries(formData);
		const json = JSON.stringify(object);

		fetch('https://api.web3forms.com/submit', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json',
				Accept: 'application/json'
			},
			body: json
		})
			.then(async (response) => {
				let json = await response.json();
				if (response.status == 200) {
					Swal.fire({
						title: 'Submitted',
						text: 'Thank you for contacting me.',
						icon: 'success',
						confirmButtonText: 'Close',
						confirmButtonColor: '#353535'
					});
				} else {
					Swal.fire({
						title: 'Hmmm.',
						text: json.message,
						icon: 'success',
						confirmButtonText: 'Close',
						confirmButtonColor: '#353535'
					});
				}
				form.reset();
			})
			.catch((error) => {
				Swal.fire({
					title: 'Error',
					text: 'something went wrong.',
					icon: 'error',
					confirmButtonText: 'Close',
					confirmButtonColor: '#353535'
				});
			});
	}
</script>

<svelte:head>
	<title>Vincent Dante - Contact Form</title>
	<meta name="description" content="Vincent Dante website" />
</svelte:head>

<div class="max-w-6xl mx-auto">
	<form
		class="flex flex-wrap gap-5 w-full md:w-1/2 mx-auto"
		on:submit|preventDefault={sendEmail}
		id="form"
	>
		<input type="hidden" name="access_key" value="f203e488-f5f2-4c53-aecb-1256788d43a2" />

		<input
			type="text"
			name="name"
			class="border border-slate-300 px-3 py-2 w-full rounded-md"
			placeholder="Full name"
			required
		/>
		<input
			type="email"
			name="email"
			class="border border-slate-300 px-3 py-2 w-full rounded-md"
			placeholder="Email address"
			required
		/>
		<textarea
			name="message"
			id=""
			cols="30"
			rows="5"
			class="border border-slate-300 px-3 py-2 w-full rounded-md"
			placeholder="Your Message"
			required
		/>
		<input
			type="submit"
			class="bg-stone-900 cursor-pointer hover:bg-stone-800 text-white px-3 py-2 w-full rounded-md"
			value="Submit"
		/>
	</form>
</div>
