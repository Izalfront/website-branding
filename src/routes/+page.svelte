<script lang="ts">
	import Ads from './Ads/Ads.svelte';
	import Contact from './Contact/Contact.svelte';
	import Footer from './Footer/Footer.svelte';
	import HomePage from './Home/HomePage.svelte';
	import Testimonials from './Testimonials/Testimonials.svelte';
	import './style/animation.css';
</script>

<div class="mx-24">
	<HomePage />
</div>
<Ads />
<div class="mx-24">
	<Testimonials />
	<Contact />
	<Footer />
</div>
