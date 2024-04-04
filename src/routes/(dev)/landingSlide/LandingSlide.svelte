<script lang="ts">
	import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { quintIn } from 'svelte/easing';
	import { fly, slide, scale } from 'svelte/transition';
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';
	import Icon from '@iconify/svelte';

	let imgSrc = [1, 2, 3, 4, 5, 6];
	let isLargeScreen = '900px';

	let node: any;

	const options = {
		rewind: true,
		perPage: 1,
		gap: '1rem',
		direction: 'ttb',
		height: '900px',
		type: 'loop',
		autoplay: true,
		arrows: false,
		pagination: false,
		speed: 1500,
		breakpoints: {
			1536: {
				height: '550px'
			}
		}
	};

	const optionsWord = {
		rewind: true,
		perPage: 1,
		gap: '1rem',
		direction: 'ttb',
		height: '900px',
		type: 'loop',
		autoplay: true,
		arrows: false,
		pagination: false,
		breakpoints: {
			1536: {
				height: '550px'
			}
		}
	}
</script>

<IntersectionObserver element={node} let:intersecting>
	<div class="flex items-center justify-center h-screen " bind:this={node}>
		<div class=" w-full max-w-[1400px]">
			<div class="flex items-center justify-between">
				<div class="w-[45%]">
					{#if intersecting}
						<div transition:fly={{ y: -80, duration: 1200, delay: 800 }}>
							<Splide aria-label="Carousel" {options} hasTrack={false} class="">
								<SplideTrack>
									{#each imgSrc as img}
										<SplideSlide class="flex">
											<div class="relative w-full">
												<div class="absolute bottom-0 right-0 w-[60%] h-[60%] cursor-grab">
													<img
														src="/assets/img/landingSection/{img}.jpeg"
														alt="Image {img}"
														class="object-cover w-full h-full rounded-2xl"
													/>
												</div>

												<div class="w-[60%] h-[60%] cursor-grab">
													<img
														src="/assets/img/landingSection2/{img}.jpeg"
														alt="Image {img}"
														class="object-cover w-full h-full rounded-2xl"
													/>
												</div>
											</div>
										</SplideSlide>
									{/each}
								</SplideTrack>
							</Splide>
						</div>
					{/if}
				</div>

				<div class="flex font-bold h1 text-[120px] w-[47%]">
					{#if intersecting}
						<div transition:fly={{ y: 80, duration: 1200, delay: 200 }}>
							<div class="mb-5 text-primary-500">
								布鲸<span class="text-white text-[90px]">社区</span>
							</div>
							
							<div class="text-3xl">全马最大的Web3社区,定位于打造成为一个友好和平的高质量交流平台</div>
							<button class=" btn bg-primary-500 h3"  transition:fly={{ x: -80, duration: 1200, delay: 1200 }}>
								加入社区 <span class="ml-2"><Icon icon="line-md:telegram" width="1.2em" height="1.2em" /></span>
							</button>
						</div>

					
					{/if}
				</div>
			</div>
		</div>
	</div>
</IntersectionObserver>
