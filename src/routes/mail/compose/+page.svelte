<script lang="ts">
	import type { Mail5Email } from '$lib/mail5';
	import { accountStore } from '$lib/store';
	import MailEditor from '$lib/components/MailEditor.svelte';
	import Header from '$lib/components/Header.svelte';
	import { fade } from 'svelte/transition';

	let email: Mail5Email = {
		from: $accountStore ? $accountStore.did : '',
		to: '',
		subject: '',
		content: '',
		attachments: [],
		status: ''
	};
</script>

<Header />

<div class="bg-color" in:fade={{ duration: 400 }}>
	<MailEditor {email} />
</div>

<style>

	.bg{
		background-color: #000000;
		background-image: linear-gradient(180deg, #000000 0%, #000000 50%, #0021fb 100%);
		
		
	}
	.bg-color{
		background-color: rgba(0, 0, 0, 0);
		border: 2px solid rgb(255, 255, 255);
		color: white;
	}


	.bg-button{
		background-color: black;
		border: 2px solid blue;
		color: white;
	}
</style>