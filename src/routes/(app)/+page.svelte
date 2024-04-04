<script lang="ts">
	import LandingSection from '../(dev)/landingSection/landingSection.svelte';
	import CarouselContainer from './home/carouselContainer/carouselContainer.svelte';
	import Trending from '../(dev)/trending/trending.svelte';
	import Videos from '../(dev)/videos/videos.svelte';
	import CryptoNews from '../(dev)/cryptoNews/cryptoNews.svelte';
    import JoinUs from '../(dev)/joinUs/joinUs.svelte';
	import Claimable from '../(dev)/claimable/claimable.svelte'
	import IntersectionObserver from 'svelte-intersection-observer';
	import PastEvents from './home/pastEvents/pastEvents.svelte';
	import Milestone from './home/milestone/milestone.svelte';
	import AboutUs from './home/aboutUs/aboutUs.svelte'
	import Partners from './home/partners/Partners.svelte';
	import LandingSlide from '../(dev)/landingSlide/LandingSlide.svelte';
	import { fly } from 'svelte/transition';
	import { scrollToSection } from '$lib/store/store'
	import { browser } from '$app/environment';

	let node: any;
	
	$: scrollToSection.subscribe(value => {
        if (value) {
            const element = document.querySelector(`#${value}`);
            if (element) {
                element.scrollIntoView({ behavior: 'smooth' });
				scrollToSection.set(null);
            }
        }
    });
	
</script>


<div class="">
	
	<!-- <LandingSection /> -->
	<div class="px-4 md:px-4 xl:px-0">
	
	<div id='home' class="">
		<!-- <LandingSlide /> -->
		<CarouselContainer />
	</div>
	
	
	 <div id="past-events">
		<PastEvents />
	</div>
	<AboutUs />
	
	
	<div id='milestone'>
		<Milestone />
	</div>
	
	<div id='partners'>
		<Partners />
	</div>
	
	</div>
	
	
</div>


<!-- <div>
	<JoinUs />
</div> -->

<!-- <div>
	<Claimable />
</div> -->




