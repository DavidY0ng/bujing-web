<script lang="ts">
	import IntersectionObserver from 'svelte-intersection-observer';
	import { quintIn } from 'svelte/easing';
	import { fly, slide, scale } from 'svelte/transition';

	let node: any;
</script>

<IntersectionObserver element={node} let:intersecting>
	<div class="flex items-center justify-center h-screen min-h-[800px]" bind:this={node}>
		{#if intersecting}
			<div class=" w-full max-w-[1400px]">
				<div class="relative">
					<div class="absolute">
						<img src="assets/img/logo/whale name.png" alt="logo" class="" />
					</div>
				</div>

				<div class="flex justify-between">
					<div class="flex items-center font-bold h1 text-[90px]">
						<div transition:fly={{ y: 80, duration: 1200, delay: 200 }}>
							<div>Community</div>
							<div>Information</div>
							<div>Hub</div>
						</div>
					</div>

					<div class="">
						<div class="relative flex gap-2">
							<div class="">
								<div class="mb-2">
									<div transition:fly={{ y: -80, duration: 1200, delay: 500 }}>
										<img
											src="/landingSection/6.jpeg"
											alt="image_1"
											class="h-[400px] w-[300px] object-cover rounded-full"
										/>
									</div>
								</div>
								<div transition:fly={{ y: 80, duration: 1200, delay: 1000 }}>
									<div
										class="rounded-full bg-secondary-500 h-[300px] w-[300px] items-center flex justify-center"
									>
										<img
											src="/landingSection/1.jpeg"
											alt="image_1"
											class="h-[280px] w-[280px] object-cover rounded-full"
										/>
									</div>
								</div>
							</div>
							<div>
								<div transition:fly={{ y: 80, duration: 1200, delay: 500 }}>
									<div
										class="rounded-full mb-2 bg-secondary-500 h-[300px] w-[300px] items-center flex justify-center"
									>
										<img
											src="/landingSection/5.jpeg"
											alt="image_1"
											class="h-[280px] w-[280px] object-cover object-center rounded-full"
										/>
									</div>
								</div>
								<div transition:fly={{ y: -80, duration: 1200, delay: 1000 }}>
									<div>
										<img
											src="/landingSection/3.jpeg"
											alt="image_1"
											class="h-[400px] w-[300px] object-cover rounded-full"
										/>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		{/if}
	</div>
</IntersectionObserver>

