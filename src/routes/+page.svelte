<script lang="ts">
	import Ads from './Ads/Ads.svelte';
	import Contact from './Contact/Contact.svelte';
	import Footer from './Footer/Footer.svelte';
	import HomePage from './Home/HomePage.svelte';
	import Testimonials from './Testimonials/Testimonials.svelte';
	import { onMount } from 'svelte';

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
</script>

<div class="text-black bg-white dark:bg-black dark:text-white">
	<button
		on:click={toggleMode}
		class="fixed left-0 bottom-8 transform -translate-x-1/2 px-4 py-2 rounded-full bg-gray-200 dark:bg-gray-800 dark:text-white shadow-lg transition-transform duration-300 hover:translate-x-0"
	>
		Toggle {isDarkMode ? 'Light' : 'Dark'} Mode
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

<!-- // import sal from 'sal.js';
// import 'sal.js/dist/sal.css';
import { onMount } from 'svelte';

// onMount(() => {
// 	// sal();
// }); -->
