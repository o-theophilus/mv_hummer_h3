<script>
	import "$lib/app.css";
	import {  isMobile, openMobileMenu } from '$lib/store.js';

	let innerWidth;
	$: $isMobile = innerWidth < 900;
	$: $openMobileMenu = !$isMobile ? false : $openMobileMenu;
</script>

<svelte:window bind:innerWidth />

<slot />
