<script lang="ts">
	import CarouselContainer from './carouselContainer/carouselContainer.svelte';
	import Trending from './trending/trending.svelte';
	import Videos from './videos/videos.svelte';
	import CryptoNews from './cryptoNews/cryptoNews.svelte';
    import JoinUs from './joinUs/joinUs.svelte';
	import Claimable from './claimable/claimable.svelte'
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';
    

	let node: any;
</script>

<div class="flex flex-col items-center ">
	<div class="max-w-[1400px] mx-auto">
		<div class="my-10">
			<CarouselContainer />
		</div>
		
		<div class="mb-10">
			<Trending />
		</div>
		
		<!-- <div class="mb-10">
			<Videos />
		</div> -->
		
		<IntersectionObserver element={node} let:intersecting once>
			<div bind:this={node}>
				{#if intersecting}
					<div transition:fly={{ y: 50, duration: 1200, delay: 200 }} class="mb-10">
						<CryptoNews />
					</div>
				{/if}
			</div>
		</IntersectionObserver>
	</div>
	
</div>


<div>
	<JoinUs />
</div>

<!-- <div>
	<Claimable />
</div> -->




