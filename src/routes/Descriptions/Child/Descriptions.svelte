<script lang="ts">
	let desc = [
		{
			title: 'Branding',
			description: `Collaborating closely, we'll develop an impactful 
            brand identity for your emerging enterprise. The 
            full spectrum of brand analysis and design is 
            addressed, culminating in a visually stunning,
            evergreen logo concept.`
		},
		{
			title: 'UX Design',
			description: `I comprehend and resolve digital product issues 
            using a user-focused methodology. Investigation, 
            compassion, and visual conveyance are a few 
            techniques I apply to captivate and involve your 
            users while fulfilling your business requirements.`
		},
		{
			title: 'UI Design',
			description: `I create efficient, adaptable, and engaging 
            websites. No predefined patterns. No sluggish, 
            complex code. Webflow forms the foundation of 
            my web development approach. I employ it to 
            provide safe, top-notch bespoke websites.`
		},
		{
			title: 'Development',
			description: `I create user-friendly, adaptive, engaging 
            websites. No cookie-cutters. No cumbersome, 
            complex coding. Webflow forms the foundation 
            of my web development approach. I employ it to 
            produce safe, top-notch personalized websites.`
		}
	];
</script>

<div class="grid md:grid-cols-2 sm:grid-cols-1 gap-x-80">
	{#each desc as description}
		<div class="pt-12">
			<h1
				data-sal-delay="300"
				data-sal="slide-up"
				data-sal-duration="500"
				class="font-semibold text-2xl py-6"
			>
				{description.title}
			</h1>
			<p
				data-sal-delay="400"
				data-sal="slide-up"
				data-sal-duration="500"
				class="font-normal text-xl"
			>
				{description.description}
			</p>
		</div>
	{/each}
</div>
