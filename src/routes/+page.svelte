<script lang="ts">
	import Ads from './Ads/Ads.svelte';
	import Contact from './Contact/Contact.svelte';
	import Footer from './Footer/Footer.svelte';
	import HomePage from './Home/HomePage.svelte';
	import Testimonials from './Testimonials/Testimonials.svelte';
	import { onMount } from 'svelte';
	import 'sal.js/dist/sal.css';
	import sal from 'sal.js';
	import './style/animation.css';

	let isDarkMode = false;

	// Function to toggle the mode
	const toggleMode = () => {
		isDarkMode = !isDarkMode;
		if (isDarkMode) {
			document.documentElement.classList.add('dark');
			localStorage.setItem('theme', 'dark');
		} else {
			document.documentElement.classList.remove('dark');
			localStorage.setItem('theme', 'light');
		}
	};

	// Set theme on mount based on previous user preference or system settings
	onMount(() => {
		const savedTheme = localStorage.getItem('theme');
		if (
			savedTheme === 'dark' ||
			(!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)
		) {
			document.documentElement.classList.add('dark');
			isDarkMode = true;
		}
	});

	onMount(() => {
		sal();
	});
</script>

<div class="text-black bg-white dark:bg-black dark:text-white">
	<button
		on:click={toggleMode}
		class="fixed left-0 bottom-8 transform -translate-x-1/2 hover:translate-x-0 p-2 rounded-full bg-gray-200 dark:bg-gray-800 shadow-lg transition-all duration-300 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500"
		aria-label={isDarkMode ? 'Switch to Light Mode' : 'Switch to Dark Mode'}
	>
		{#if isDarkMode}
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6 text-yellow-400"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
				/>
			</svg>
		{:else}
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6 text-gray-900"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
				/>
			</svg>
		{/if}
	</button>
	<div class="mx-10 md:mx-24 sm:mx-10">
		<HomePage />
	</div>
	<Ads />
	<div class="mx-10 md:mx-24 sm:mx-10">
		<Testimonials />
		<Contact />

		<Footer />
	</div>
</div>
