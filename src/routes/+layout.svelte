<script lang="ts">
	import '../app.postcss';
	import '@fortawesome/fontawesome-free/css/all.min.css';
	import { Toast } from '@skeletonlabs/skeleton';
	import process from 'process';
	import { Buffer } from 'buffer';
	import EventEmitter from 'events';
	import { browser } from '$app/environment';
	import { initializeStores } from '@skeletonlabs/skeleton';

	initializeStores();

	if (browser) {
		window.Buffer = Buffer;
		window.process = process;
		(window as any).EventEmitter = EventEmitter;
		window.global = window;
	}
</script>

<Toast position="b" buttonDismiss="" class ="bg-color" />
<slot />
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