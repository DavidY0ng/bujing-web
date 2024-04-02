<script lang="ts">
	import { filter, NoirLight, Rustic } from '@skeletonlabs/skeleton';
	import Activity_DATA from './activity-data.json';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly, fade, slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import { browser } from '$app/environment';

	let node: any;
	let expandedCardId = 0;

	const onExpand = (id: number) => {
		if (expandedCardId === id) {
			expandedCardId = null; // Collapse the card if it's already expanded
		} else {
			expandedCardId = id; // Expand the clicked card
		}
	};
</script>

<NoirLight />
<Rustic />
<!-- <div class="flex justify-center w-full bg-gradient-to-b from-tertiary-500 via-white to-white"> -->
<div class="flex justify-center w-full bg-surface-900">
	<div class="lg:pb-[200px] md:pt-[100px] md:pb-[100px] pt-[30px] pb-[30px] md:max-w-[1400px] w-full">
		<!-- <IntersectionObserver element={node} let:intersecting once>
			<div bind:this={node}>
				{#if intersecting} -->
					<div transition:fly={{ y: -80, duration: 1200, delay: 200 }}>
						<div class="mb-5 font-bold h1">过去活动</div>
						<div class="h3 mb-10 md:w-[70%]">
							浏览我们曾举办的精彩活动，回顾过往时光，获得灵感。
						</div>
					</div>
				<!-- {/if}
			</div>
		</IntersectionObserver> -->
		<IntersectionObserver element={node} let:intersecting once>
			<div bind:this={node}>
				<div class="flex flex-col justify-between gap-4 overflow-x-auto md:flex-row xl:overflow-hidden">
					{#each Activity_DATA as data, i}
						{#if intersecting}
							<div transition:fly={{ x: -100, duration: 1200, delay: 600 * i }}>
								{#if expandedCardId === data.id}
									<div class="card md:h-[400px] md:w-[500px] w-full rounded-3xl relative shadow-md h-[250px]">
										<img
											src="/pastActivity/{data.img}"
											alt="img 1"
											class="md:h-[400px] md:w-[500px] h-[250px] w-full rounded-3xl absolute object-cover"
										/>
										<div
											class="absolute bottom-0 w-full bg-gray-500 opacity-50 h-[50%] rounded-b-3xl"
										></div>
										<div class="absolute font-bold text-white md:bottom-40 bottom-[36%] left-5 h3">
											{data.title}
										</div>
										<div class="hidden md:block absolute text-white bottom-[25%] left-5 font-semibold">
											{data.description}
										</div>
										<a href={data.href} target="_blank">
											<button
												class="absolute text-white bg-surface-800 bottom-5 btn z-99 hover:variant-filled-primary hover:dark:text-white left-5"
											>
												浏览
											</button>
										</a>
									</div>
								{:else}
									<!-- svelte-ignore a11y-click-events-have-key-events -->
									<!-- svelte-ignore a11y-no-static-element-interactions -->
									<div
										on:click={() => onExpand(data.id)}
										class="card md:h-[400px] md:w-[200px] w-full h-[100px] rounded-3xl relative shadow-md cursor-pointer"
									>
										<img
											src="/pastActivity/{data.img}"
											use:filter={'#Rustic'}
											alt="img 1"
											class="md:h-[400px] md:w-[200px] h-[100px] w-full rounded-3xl absolute opacity-30 object-cover"
										/>
										<div
											class="absolute w-[300px] font-bold text-white md:-rotate-90 md:bottom-40 top-5 md:left-0 left-5 h3 origin-center"
										>
											{data.title}
										</div>
									</div>
								{/if}
							</div>
						{:else}
						<div class="h-[857px]">
							
						</div>
						{/if}
					{/each}
				</div>
			</div>
		</IntersectionObserver>
	</div>
</div>
