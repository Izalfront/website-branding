<script lang="ts">
	let data = [
		{
			name: 'Crtyl',
			title: 'Mobile App',
			image: './card1.png'
		},
		{
			name: 'Tansto',
			title: 'Web Design',
			image: './card2.png'
		},
		{
			name: 'Senta',
			title: 'Mobile App & Branding',
			image: './card3.png'
		},
		{
			name: 'Crint',
			title: 'Mobile App',
			image: './card4.png'
		}
	];
</script>

<div>
	<div class="grid md:grid-cols-2 gap-6 sm:grid-cols-1">
		{#each data as datas}
			<div class="grid">
				<img
					data-sal-delay="300"
					data-sal="slide-up"
					data-sal-duration="500"
					class="w-full h-full"
					src={datas.image}
					alt=""
				/>
				<div data-sal-delay="400" data-sal="slide-up" data-sal-duration="500" class="pt-6 text-xl">
					<h1 class="font-bold">{datas.name}</h1>
					<h1>{datas.title}</h1>
				</div>
			</div>
		{/each}
	</div>
</div>
