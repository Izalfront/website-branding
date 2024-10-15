<script lang="ts">
	import Ads from './Ads/Ads.svelte';
	import Contact from './Contact/Contact.svelte';
	import Footer from './Footer/Footer.svelte';
	import HomePage from './Home/HomePage.svelte';
	import Testimonials from './Testimonials/Testimonials.svelte';
	import './style/animation.css';
</script>

<div class="mx-10 md:mx-24 sm:mx-10">
	<HomePage />
</div>
<Ads />
<div class="mx-10 md:mx-24 sm:mx-10">
	<Testimonials />
	<Contact />
	<Footer />
</div>
