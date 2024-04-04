<script lang="ts">
	// import { AppShell } from '@skeletonlabs/skeleton';
	import Icon from '@iconify/svelte';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';
	import { fade } from 'svelte/transition';
	import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
	import { browser } from '$app/environment';

	let node: any;
	const socialImg = [1, 2, 3, 4, 5, 6, 7];
	const articleInfos = [
		{
			img: '1',
			title: 'CRYPTO ON THE RISE',
			subtitle: 'Understanding crypto bull market.',
			author: 'David Hoffman',
			day: '1 day ago'
		},
		{
			img: '2',
			title: 'CRYPTO ON THE RISE',
			subtitle: 'hello',
			author: 'William Pester',
			day: '1 day ago'
		},
		{
			img: '3',
			title: 'Why buy',
			subtitle: 'hello',
			author: 'David Hoffman',
			day: '1 day ago'
		}
	];

	const latestInfos = [
		{
			title: '金色电音节',
			category: '活动',
			time: '3月23日',
			href: 'https://twitter.com/bujingmalaysia/status/1767513240081490019',
			signup: 'https://jinse.cn/blockchain/3677157.html'
		},
		{
			title: "Bitcoin's $70,000 Question",
			category: 'TODAY IN MARKETS',
			time: '1 day ago'
		},
		{
			title: 'When will Altcoin Season Arrive?',
			category: 'ANALYSIS',
			time: '2 days ago'
		},
		{
			title: 'When will Altcoin Season Arrive?',
			category: 'ANALYSIS',
			time: '2 days ago'
		}
	];

	const options = {
		rewind: true,
		perPage: 1,
		gap: '1rem',
		type: 'loop',
		autoplay: true,
		arrows: false,
		pagination: false,
		speed: 1500,
		breakpoints: {
			768: {}
		}
	};

	const enlarge = () => {};
</script>

<IntersectionObserver element={node} let:intersecting once>
	<div bind:this={node} class="">
		{#if intersecting}
			<div class="flex justify-center mt-[20px]">
				<div class=" w-full max-w-[1400px]">
					<div class="flex flex-col gap-5 lg:flex-row bg-surface-900">
						<div class="lg:w-[150%] cursor-grab">
							<div transition:fly={{ x: -80, duration: 1200, delay: 1400 }}>
								<Splide {options} hasTrack={false}>
									<SplideTrack>
										{#each socialImg as img}
											<SplideSlide>
												<div class="">
													<div class="flex justify-center rounded-xl">
														<img
															src="assets/img/social/{img}.jpeg"
															alt="social {img}"
															class="object-cover w-full md:h-[500px] h-[300px] rounded-xl"
														/>
													</div>
												</div>
											</SplideSlide>
										{/each}
									</SplideTrack>
									<div class="splide__progress">
										<div class="splide__progress__bar"></div>
									</div>
								</Splide>
							</div>
						</div>

						<div class="flex flex-col gap-4">
							<!-- latest news -->
							<div
								class="flex flex-col justify-between h-full p-4 border rounded-2xl border-secondary-800"
							>
								<div>
									<div class="flex justify-center mb-5 text-xl font-bold">
										<div class="h-full w-[200px] mr-5 items-center flex">
											<div transition:fly={{ y: -80, duration: 1200, delay: 400 }}>
												<img src="assets/img/logo/whale name.png" alt="bujing" class="w-full h-full" />
											</div>
										</div>
									</div>

									<div transition:fly={{ y: -80, duration: 1200, delay: 600 }}>
										<div class="mb-5 font-bold underline h3 text-secondary-400">
											优质社区由优秀的人群组成
										</div>
									</div>

									<div class="flex flex-col text-xl text-white">
										<div transition:fly={{ y: -80, duration: 1200, delay: 800 }}>
											<p class="mb-5">八卦 日常生活，了解各行各业的发展，关注币圈信息及知识。</p>

											<div transition:fly={{ y: -80, duration: 1200, delay: 1000 }}>
												<p>
													本社区 NFT
													没有任何炒作空间，买了也不升值，所以没有打算加入社区的人就别搞了。
												</p>
											</div>
										</div>
									</div>
								</div>

								<div>
									<hr class="my-3 !border-gray-700" />

									<div transition:fly={{ y: 80, duration: 1200, delay: 400 }}>
										<div class="mb-5 text-lg font-bold text-center text-gray-500">社交平台</div>

										<div class="flex justify-center gap-4 text-white">
											<a href="https://t.me/bujingpublic" target="blank">
												<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
													<Icon icon="mingcute:telegram-fill" width="1.2em" height="1.2em" />
												</button>
											</a>

											<a href="https://twitter.com/bujingmalaysia" target="blank">
												<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
													<Icon icon="ri:twitter-x-fill" width="1.2em" height="1.2em" />
												</button>
											</a>

											<a href="https://www.facebook.com/groups/bujing" target="blank">
												<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
													<Icon icon="ri:facebook-fill" width="1.2em" height="1.2em" />
												</button>
											</a>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		{:else}
			<div class="h-[503px]">
				
			</div>
		{/if}
	</div>
</IntersectionObserver>
