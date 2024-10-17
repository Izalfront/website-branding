<script lang="ts">
	import CardContent from '../Cards/CardContent.svelte';
	import DescriptionContent from '../Descriptions/DescriptionContent.svelte';
	import { onMount } from 'svelte';

	let activeTab = 'Home'; // Default tab
	let isMenuOpen = false;

	// Function to handle tab click
	const handleTabClick = (tab: string) => {
		activeTab = tab;
		isMenuOpen = false;
	};

	// Toggle menu for mobile
	const toggleMenu = () => {
		isMenuOpen = !isMenuOpen;
	};

	// Close menu when clicking outside
	onMount(() => {
		const handleClickOutside = (event: MouseEvent) => {
			const target = event.target as HTMLElement;
			if (!target.closest('nav') && !target.closest('#menuToggle')) {
				isMenuOpen = false;
			}
		};

		document.addEventListener('click', handleClickOutside);

		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<div class="px-4 md:px-0 lg:px-16">
	<div
		class="md:block px-10 lg:px-20 flex justify-between items-center bg-white md:pb-8 fixed top-0 left-0 right-0 z-50"
	>
		<!--   class="fixed top-0 left-0 right-0 bg-white shadow-md z-50" -->
		<div
			data-sal-delay="300"
			data-sal="slide-down"
			data-sal-duration="500"
			class="flex items-center justify-center pt-8 pb-10 lg:pt-12 lg:pb-14"
		>
			<img class="w-20 md:w-28 lg:w-36" src="./Joey.png" alt="Joey logo" />
		</div>
		<!-- Header start -->
		<header data-sal-delay="300" data-sal="slide-up" data-sal-duration="500" class="relative">
			<nav class="flex justify-center md:block">
				<!-- Mobile menu button -->
				<!-- svelte-ignore a11y_consider_explicit_label -->
				<button
					id="menuToggle"
					class="md:hidden z-20 bg-black text-white p-2 rounded-full"
					on:click={toggleMenu}
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						/>
					</svg>
				</button>
				<!-- Desktop and Mobile menu -->
				<ul
					class="{isMenuOpen
						? 'flex'
						: 'translate-x-full'} md:translate-x-0 md:opacity-100 transition-all duration-300 ease-in-out fixed md:relative top-0 right-0 h-fit w-64 md:w-fit md:mx-auto flex flex-col md:flex-row p-4 md:p-1 space-y-2 md:space-y-0 md:space-x-4 items-start justify-start md:items-center bg-black text-white md:bg-black md:rounded-full z-40 rounded-bl-2xl"
				>
					<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
					{#each ['Home', 'Projects', 'About', 'Contact'] as tab}
						<!-- svelte-ignore a11y_click_events_have_key_events -->
						<li
							class="w-full md:w-auto text-center {activeTab === tab
								? 'bg-white text-black'
								: 'bg-black text-white'} px-4 py-2 rounded-full font-medium cursor-pointer transition-all duration-300 ease-in-out"
							on:click={() => handleTabClick(tab)}
						>
							<!-- svelte-ignore a11y_invalid_attribute -->
							<a href="#">{tab}</a>
						</li>
					{/each}
				</ul>
			</nav>
		</header>
	</div>
	<!-- header end -->

	<div
		data-sal-delay="500"
		data-sal="slide-up"
		data-sal-duration="500"
		class="flex items-center justify-start pt-72 pb-12 text-7xl sm:text-[8rem] md:text-[12rem] lg:text-[16rem]"
	>
		<div class="block font-semibold leading-none">
			<h1 class="mb-0">Websites&</h1>
			<h1 class="mb-0">Branding</h1>
		</div>
	</div>
	<div
		data-sal-delay="600"
		data-sal="fade"
		data-sal-duration="500"
		class="relative cursor-pointer hidden md:block"
	>
		<h1
			class="uppercase absolute left-[60%] md:left-[70%] px-6 lg:left-[75%] pb-[5%] pl-[3%] bottom-[2rem] text-2xl lg:text-3xl font-bold flex items-center gap-2 animate-bouncesmall"
		>
			Scroll Down
			<svg
				width="20"
				height="20"
				viewBox="0 0 13 16"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g clip-path="url(#clip0_37_21106)">
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M7.02722 13.1657C7.3145 12.8537 7.66169 12.4914 8.05373 12.1103C9.1898 11.0057 10.745 9.70094 12.335 9.03846L12.7196 9.96154C11.3095 10.5491 9.86474 11.7443 8.75081 12.8272C8.1993 13.3634 7.73931 13.8617 7.41747 14.2257C7.25668 14.4076 7.13071 14.5555 7.04541 14.6574C7.00277 14.7083 6.97032 14.7477 6.94878 14.7741L6.92477 14.8036L6.91909 14.8106L6.91785 14.8122L6.52727 15.3004L6.1369 14.8124L6.13545 14.8106L6.12976 14.8036L6.10575 14.7741C6.08422 14.7477 6.05177 14.7083 6.00912 14.6574C5.92383 14.5555 5.79786 14.4076 5.63707 14.2257C5.31523 13.8617 4.85524 13.3634 4.30373 12.8272C3.1898 11.7443 1.74502 10.5491 0.334961 9.96154L0.719576 9.03846C2.30951 9.70094 3.86474 11.0057 5.00081 12.1103C5.39281 12.4914 5.73996 12.8537 6.02722 13.1656V0.5H7.02722V13.1657Z"
						fill="black"
						stroke="black"
					/>
				</g>
				<defs>
					<clipPath id="clip0_37_21106">
						<rect width="13" height="15" fill="white" transform="translate(0 0.5)" />
					</clipPath>
				</defs>
			</svg>
		</h1>
	</div>
	<div
		data-sal-delay="800"
		data-sal="slide-up"
		data-sal-duration="500"
		class="pt-16 flex flex-col md:flex-row justify-between gap-8 md:gap-0"
	>
		<div class="text-xl md:text-2xl">
			<h1 class="pb-2 font-bold">Lets Talk</h1>
			<h1 class="font-normal">hello@joey.co</h1>
		</div>

		<div data-sal-delay="900" data-sal="slide-up" data-sal-duration="500">
			<h1 class="text-xl md:text-2xl">
				Hello, I'm Joey, an online product designer focusing <br class="hidden md:inline" /> on
				brand identity, advertising, and no-code <br class="hidden md:inline" /> instruments.
			</h1>
		</div>
	</div>
	<div>
		<CardContent />
	</div>
	<div>
		<DescriptionContent />
	</div>
</div>
