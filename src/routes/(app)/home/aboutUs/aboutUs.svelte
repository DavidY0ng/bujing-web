<script lang="ts">
	import Icon from '@iconify/svelte';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly, slide, scale } from 'svelte/transition';
	import Symbol from '$lib/components/materialSymbol/symbol.svelte';
	import { filter, NoirLight, Rustic, BlueNight } from '@skeletonlabs/skeleton';
	import { quintOut } from 'svelte/easing';

	let node: any;

	let aboutUSData = [
		{
			icon: 'fa:bitcoin',
			title: '秉承Web3发展'
		},
		{
			icon: 'mdi:share-variant',
			title: '理念分享'
		},
		{
			icon: 'heroicons:chat-bubble-left-right-20-solid',
			title: '吹水度日'
		}
	];
</script>

<NoirLight />
<Rustic />
<BlueNight />

<div class="relative flex justify-center">
	<img
		src="assets/img/aboutUs/bg1.jpg"
		use:filter={'#BlueNight'}
		alt="bg"
		class=" object-cover opacity-20 w-full md:h-[800px] h-[550px]"
	/>

	<div class="flex max-w-[1400px] w-full absolute">
		<div class="flex lg:flex-row flex-col lg:py-[150px] py-[30px] px-5 lg:px-0">
			<div class="lg:w-[170%] md:mr-5 relative lg:h-[550px] lg:pl-10 w-full mb-5 md:mb-5">
				<!-- <div class="bg-primary-400 h-[300px] w-[300px] absolute left-0 top-5">
					
				</div> -->
				<IntersectionObserver element={node} let:intersecting once>
					<div bind:this={node}>
						<div class="flex justify-center lg:absolute lg:bottom-0">
							{#if intersecting}
								<img
									src="assets/img/aboutUs/1.jpeg"
									alt="1"
									class="md:h-[500px] lg:w-[420px] w-full h-[250px] object-cover object-top"
									transition:fly={{
										x: -80,
										duration: 1200,
										delay: 1400
									}}
								/>
							{/if}
						</div>

						<div class="hidden xl:block absolute top-0 flex left-[64%]">
							{#if intersecting}
								<img
									src="assets/img/aboutUs/2.jpeg"
									alt="1"
									class="h-[240px] w-[190px] object-cover object-left"
									transition:fly={{
										y: -80,
										duration: 1200,
										delay: 400
									}}
								/>
							{/if}
						</div>

						<div class="hidden xl:block absolute top-[47%] flex left-[64%]">
							{#if intersecting}
								<img
									src="assets/img/aboutUs/4.jpeg"
									alt="1"
									class="h-[220px] w-[240px] object-cover object-right"
									transition:fly={{
										y: 80,
										duration: 1200,
										delay: 400
									}}
								/>
							{/if}
						</div>
					</div>
				</IntersectionObserver>
			</div>

			<div class="flex items-center">
				<div class="justify-between text-white">
					<IntersectionObserver element={node} let:intersecting once>
						<div bind:this={node}>
							{#if intersecting}
								<div
									class="mb-5 font-bold lg:mb-20 md:mb-5 h1"
									transition:fly={{
										y: -80,
										duration: 1200,
										delay: 600
									}}
								>
									我们的宗旨
								</div>
								<div
									class="md:mb-[60px] h3"
									transition:fly={{
										y: 80,
										duration: 1200,
										delay: 600
									}}
								>
									布鲸社区创立于2021年1月，秉承Web3和社区化的发展理念，定位于打造成为一个友好和平的高质量交流平台。
									在这里，您会遇到加密币圈的爱好者，区块链项目的交流，新闻及各大项目理念分享。
								</div>
							{/if}
						</div>
					</IntersectionObserver>
				</div>

				<!-- <div class="flex justify-between">
							{#each aboutUSData as data, i}
								{#if intersecting}
									<div
										class="flex flex-col items-center p-4 py-10 rounded-2xl variant-glass-primary h-[200px] w-[200px] justify-between"
										transition:scale={{
											duration: 400,
											delay: 600,
											opacity: 0,
											start: 0.5,
											easing: quintOut
										}}
									>
										<Icon icon={data.icon} width="5em" height="5em" />
										<div class="mt-3 text-center h3">
											{data.title}
										</div>
									</div>
								{/if}
							{/each}
						</div> -->
			</div>
		</div>
	</div>
</div>

<!-- <div
	class="flex justify-center w-full bg-[url('/aboutUs/1.jpg')] bg-no-repeat bg-cover"
	style="filter: url({'#BlueNight'})"
>
	<div class="flex max-w-[1400px] w-full">
		<div class="flex py-[300px]">
			<IntersectionObserver element={node} let:intersecting once>
				<div bind:this={node} class="w-[110%]">
					{#if intersecting}
						<div transition:fly={{ y: -80, duration: 1200, delay: 200 }}>
							<div class="mb-5 font-bold h1">我们的宗旨</div>
						</div>
					{/if}
				</div>
			</IntersectionObserver>

			<div class="">
				<div>
					<IntersectionObserver element={node} let:intersecting once>
						<div bind:this={node}>
							{#if intersecting}
								<div class="mb-[60px] h3" transition:fly={{ y: -80, duration: 1200, delay: 200 }}>
									布鲸社区创立于2021年1月，秉承Web3和社区化的发展理念，定位于打造成为一个友好和平的高质量交流平台。
									在这里，您会遇到加密币圈的爱好者，区块链项目的交流，新闻及各大项目理念分享。
								</div>
							{/if}
						</div>
					</IntersectionObserver>
				</div>

				<div class="flex justify-between">
					<IntersectionObserver element={node} let:intersecting once>
						{#each aboutUSData as data, i}
							{#if intersecting}
								<div
									bind:this={node}
									class="p-4 rounded-2xl variant-glass-primary"
									transition:scale={{
										duration: 400,
										delay: 600,
										opacity: 0,
										start: 0.5,
										easing: quintOut
									}}
								>
									<Icon icon={data.icon} width="10em" height="10em" />
									<div class="mt-3 text-center h3">
										{data.title}
									</div>
								</div>
							{/if}
						{/each}
					</IntersectionObserver>
				</div>
			</div>
		</div>
	</div>
</div> -->
