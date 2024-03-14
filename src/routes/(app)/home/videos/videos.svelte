<script lang="ts">
	import Icon from '@iconify/svelte';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';

	let node: any;
</script>

<IntersectionObserver element={node} let:intersecting once>
	<div bind:this={node}>
		{#if intersecting}
			<div transition:fly={{ y: 50, duration: 1200, delay: 200 }}>
				<div class="mb-8 font-bold h2">VIDEOS</div>

				<div class="flex w-full gap-4">
					<div class="">
						<a href="#">
							<img
								src="/trending/shiba coin.png"
								alt="img"
								class="object-cover object-top h-[505px] w-[900px] rounded-xl"
							/>
							<div class="flex items-center pt-5 pb-1">
								<span class="pr-3">
									<Icon icon="octicon:play-16" width="1.2em" height="1.2em" />
								</span>
								<div class="font-bold">
									Who let the dogs out? - Justin Sun on Meme, Crypto, and Why Dog?
								</div>
							</div>
							<div class="text-sm text-gray-500">1 day ago</div>
						</a>
					</div>

					<div class="flex flex-col max-w-[500px] gap-2">
						<div class="flex">
							<div class="mr-3">
								<img
									src="/trending/shiba coin.png"
									alt="img"
									class="object-cover object-top rounded-lg max-h-[120px] min-w-[180px] max-w-[180px] flex-shrink-0"
								/>
							</div>

							<div class="pb-1">
								<div class="mb-1 font-bold">
									<span>
										<Icon icon="octicon:play-16" width="1.6em" height="1.6em" class="mr-1" />
									</span>
									<div>Who let the dogs out? - Justin Sun on Meme, Crypto, and Why Dog?</div>
								</div>
								<div class="text-sm text-gray-500">Today</div>
							</div>
						</div>

						<div class="flex">
							<div class="mr-3">
								<img
									src="/trending/shiba coin.png"
									alt="img"
									class="object-cover object-top rounded-lg h-[120px] min-w-[180px] max-w-[180px] flex-shrink-0"
								/>
							</div>

							<div class="pb-1">
								<div class="mb-1 font-bold">
									<span>
										<Icon icon="octicon:play-16" width="1.6em" height="1.6em" class="mr-1" />
									</span>
									<div>Who let the dogs out? - Justin Sun on Meme, Crypto, and Why Dog?</div>
								</div>
								<div class="text-sm text-gray-500">Today</div>
							</div>
						</div>

						<div class="flex">
							<div class="mr-3">
								<img
									src="/trending/shiba coin.png"
									alt="img"
									class="object-cover object-top rounded-lg h-[120px] min-w-[180px] max-w-[180px] flex-shrink-0"
								/>
							</div>

							<div class="pb-1">
								<div class="mb-1 font-bold">
									<span>
										<Icon icon="octicon:play-16" width="1.6em" height="1.6em" class="mr-1" />
									</span>
									<div>Who let the dogs out? - Justin Sun on Meme, Crypto, and Why Dog?</div>
								</div>
								<div class="text-sm text-gray-500">Today</div>
							</div>
						</div>

						<div class="flex">
							<div class="mr-3">
								<img
									src="/trending/shiba coin.png"
									alt="img"
									class="object-cover object-top rounded-lg h-[120px] min-w-[180px] max-w-[180px] flex-shrink-0"
								/>
							</div>

							<div class="pb-1">
								<div class="mb-1 font-bold">
									<span>
										<Icon icon="octicon:play-16" width="1.6em" height="1.6em" class="mr-1" />
									</span>
									<div>Who let the dogs out? - Justin Sun on Meme, Crypto, and Why Dog?</div>
								</div>
								<div class="text-sm text-gray-500">Today</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		{/if}
	</div>
</IntersectionObserver>
