<script lang="ts">
	import CardContent from '../Cards/CardContent.svelte';
	import DescriptionContent from '../Descriptions/DescriptionContent.svelte';

	let activeTab = 'Home'; // Default tab

	// Function to handle tab click
	const handleTabClick = (tab: string) => {
		activeTab = tab;
	};
</script>

<div>
	<div class="flex items-center justify-center pt-8 pb-10">
		<img class="w-20" src="./Joey.png" alt="" />
	</div>
	<!-- Header start -->
	<header>
		<nav>
			<!-- svelte-ignore a11y_click_events_have_key_events -->
			<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
			<ul
				class="flex space-x-4 items-center justify-center py-1 px-1 bg-black text-white rounded-full w-fit mx-auto"
			>
				<li
					class:bg-white={activeTab === 'Home'}
					class:text-black={activeTab === 'Home'}
					class:bg-black={activeTab !== 'Home'}
					class:text-white={activeTab !== 'Home'}
					class="px-4 py-2 rounded-full font-medium cursor-pointer transition-all duration-300 ease-in-out"
					onclick={() => handleTabClick('Home')}
				>
					<a href="#">Home</a>
				</li>
				<li
					class:bg-white={activeTab === 'Projects'}
					class:text-black={activeTab === 'Projects'}
					class:bg-black={activeTab !== 'Projects'}
					class:text-white={activeTab !== 'Projects'}
					class="px-4 py-2 rounded-full font-medium cursor-pointer transition-all duration-300 ease-in-out"
					onclick={() => handleTabClick('Projects')}
				>
					<a href="#">Projects</a>
				</li>
				<!-- svelte-ignore a11y_click_events_have_key_events -->
				<li
					class:bg-white={activeTab === 'About'}
					class:text-black={activeTab === 'About'}
					class:bg-black={activeTab !== 'About'}
					class:text-white={activeTab !== 'About'}
					class="px-4 py-2 rounded-full font-medium cursor-pointer transition-all duration-300 ease-in-out"
					onclick={() => handleTabClick('About')}
				>
					<a href="#">About</a>
				</li>
				<!-- svelte-ignore a11y_click_events_have_key_events -->
				<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
				<li
					class:bg-white={activeTab === 'Contact'}
					class:text-black={activeTab === 'Contact'}
					class:bg-black={activeTab !== 'Contact'}
					class:text-white={activeTab !== 'Contact'}
					class="px-4 py-2 rounded-full font-medium cursor-pointer transition-all duration-300 ease-in-out"
					onclick={() => handleTabClick('Contact')}
				>
					<a href="#">Contact</a>
				</li>
			</ul>
		</nav>
	</header>
	<!-- header end -->
	<div class="flex items-center justify-start pt-12 pb-12 text-[16rem]">
		<div class="block font-semibold leading-none">
			<h1 class="mb-0">Websites&</h1>
			<h1 class="mb-0">Branding</h1>
		</div>
	</div>
	<div class="relative cursor-pointer">
		<h1
			class="uppercase absolute left-[70%] pb-[5%] pl-[3%] bottom-[35%] text-2xl font-bold flex items-center gap-2 hover:animate-bouncesmall"
		>
			Scroll Down <svg
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

	<div class="pt-16 flex justify-between">
		<div class="text-2xl">
			<h1 class="pb-2 font-bold">Lets Talk</h1>
			<h1 class="font-normal">hello@joey.co</h1>
		</div>

		<div>
			<h1 class="text-2xl">
				Hello, I'm Joey, an online product designer focusing <br /> on brand identity, advertising,
				and no-code <br /> instruments.
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
