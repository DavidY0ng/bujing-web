<script lang="ts">
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly, scale } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import Icon from '@iconify/svelte';

	let node: any;

	const milestoneData = [
		{
			title: 'Telegram 起步',
			subtitle: '开始了社交媒体的探索和建立。',
			date: 'MAR 2021',
			icon: 'iconoir:telegram'
		},
		{
			title: '首次聚会',
			subtitle: '初次见面,共同探讨未来方向.',
			
			date: 'AUG 2022',
			icon: 'tabler:social'
		},
		{
			title: 'Twitter 启动',
			subtitle: '正式启动新社交平台，促进成员交流、分享想法和互动。',
			date: 'AUG 2023',
			icon: 'pajamas:twitter'
		},
		{
			title: '1000+ 成员',
			subtitle: '更多即将到来!',
			date: 'JAN 2024',
			icon: 'fluent:people-team-28-filled'
		},
		{
			title: '持续我们的旅程',
			subtitle: '',
			date: '现今',
			icon: 'fluent-emoji:spouting-whale'
		}
	];
</script>

<div class="flex justify-center w-full bg-[url('/assets/img/milestone/1.jpg')] text-black bg-no-repeat bg-cover">
	<div class="py-20 md:max-w-[1400px] w-full">
		<IntersectionObserver element={node} let:intersecting once>
			<div bind:this={node}>
				{#if intersecting}
					<div transition:fly={{ y: -80, duration: 500, delay: 700 }}>
						<div class="mb-10 font-bold text-center h1">我们的旅程</div>
						<!-- <div class="h3 mb-10 w-[70%]">
							These projects demonstrate my expertise with practical examples of some of my work,
							including brief descriptions and links to code repositories and live demos.
						</div> -->
					</div>
				{/if}
			</div>
		</IntersectionObserver>

		<div class="relative w-full py-5">
			<div
				class="h-full top-0 md:left-[50%] left-[15%] absolute divider-vertical !border-r-2 !border-gray-400 md:-translate-x-[50%] z-1"
			></div>
			<IntersectionObserver element={node} let:intersecting once>
				<div bind:this={node}>
					{#each milestoneData as data, index}
						{#if intersecting}
							<div class="flex mb-10 h-[150px] relative">
								<!-- card -->

								<div
									transition:fly={{
										x: index % 2 === 0 ? -100 : 100,
										duration: 500,
										delay: 700 * index
									}}
									class="md:w-[30%] w-[70%] p-[1.5em] shadow-lg card bg-secondary-800 absolute {index % 2 === 0
										? 'md:left-[14%]  left-[25%] '
										: 'md:right-[14%] right-[5%]'} md:top-[15%] top-[25%] "  
								>
								<div class="font-bold text-gray-400 md:hidden h3">
									{data.date}
								</div>
									<div class="mb-2 font-bold text-white h3">{data.title}</div>

									{#if data.date !== '现今'}
										<div class="font-semibold text-gray-200">{data.subtitle}</div>
									{:else}
										<a href="https://t.me/bujingpublic" target="_blank">
											<button class="text-white btn bg-primary-400">
												加入我们 <span class="ml-2"
													><Icon icon="iconoir:telegram" width="1.2em" height="1.2em" /></span
												>
											</button>
										</a>
									{/if}
								</div>
								<!-- icon -->
								<div class="flex items-center">
									<div
										transition:scale={{
											duration: 1000,
											delay: 700 * index,
											opacity: 0,
											start: 0.5,
											easing: quintOut
										}}
										class="absolute flex items-center justify-center {data.date !== 'PRESENT'
											? 'bg-gray-400/50'
											: 'bg-primary-500/50'} w-[70px] h-[70px] rounded-full md:left-[50%] left-[15%] -translate-x-[50%]"
									>
										<div
											class=" w-[60px] h-[60px] bg-secondary-900 rounded-full flex justify-center items-center"
										>
											<Icon icon={data.icon} width="1.8em" height="1.8em" color="white" class="" />
										</div>
									</div>

									<!-- date -->
									<div
										transition:fly={{
											x: index % 2 === 0 ? 100 : -100,
											duration: 500,
											delay: 700 * index
										}}
										class="hidden md:block absolute flex font-bold text-gray-400 h3 {index % 2 == 0
											? 'left-[55%]'
											: 'right-[55%]'}"
									>
										{data.date}
									</div>
								</div>
							</div>
						{/if}
					{/each}
				</div>
			</IntersectionObserver>
		</div>
	</div>
</div>
