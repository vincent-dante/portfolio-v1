<script>
	import emailjs from '@emailjs/browser';
	import Swal from 'sweetalert2';
	import { PUBLIC_SERVICE_ID, PUBLIC_TEMPLATE_ID, PUBLIC_KEY } from '$env/static/public';

	function sendEmail(e) {
		emailjs.sendForm(PUBLIC_SERVICE_ID, PUBLIC_TEMPLATE_ID, e.target, PUBLIC_KEY).then(
			(result) => {
				document.getElementById('myForm').reset();
				Swal.fire({
					title: 'Submitted',
					text: 'Thank you for contacting me.',
					icon: 'success',
					confirmButtonText: 'Close',
					confirmButtonColor: '#353535'
				});
			},
			(error) => {
				Swal.fire({
					title: 'Error',
					text: 'something went wrong.',
					icon: 'error',
					confirmButtonText: 'Close',
					confirmButtonColor: '#353535'
				});
			}
		);
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
		id="myForm"
	>
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
