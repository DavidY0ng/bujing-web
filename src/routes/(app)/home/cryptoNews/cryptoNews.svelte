<script lang="ts">
	import Icon from '@iconify/svelte';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';
	import { fade } from 'svelte/transition';

	let intersecting: any;
	let element:any
</script>

<IntersectionObserver {element} bind:intersecting once threshold={1}>
	<div bind:this={element}>
		{#if intersecting}
			<div transition:fly={{ y: 50, duration: 1200, delay: 200 }}>
				<div class="flex justify-between">
					<div class="mb-8 font-bold h2">CRYPTO NEWS</div>
					<a class="flex text-primary-500 hover:underline" href="#"> More from Crypto News > </a>
				</div>

				<div class="grid grid-cols-4 gap-4">
					<a class="" href="#">
						<div class="pb-5">
							<img
								src="/trending/shiba coin.png"
								alt="trending_image"
								class="object-cover object-top h-48 rounded-2xl w-96"
							/>
						</div>

						<div class="text-lg font-semibold">Why is SHIB surging?</div>
						<div class="mb-2 text-sm">
							SHIB is on the rise, everyone is getting crazy asldkasld alksdjlaksd jalksdjla jlaksdj
						</div>

						<div class="flex">
							<code class="mr-5 code"> Analysis </code>

							<div class="text-xs text-gray-500">2 weeks ago</div>
						</div>
					</a>

					<div>
						<div class="pb-5">
							<img
								src="/trending/bitcoin rising.png"
								alt="trending_image"
								class="object-cover h-48 rounded-2xl w-96"
							/>
						</div>

						<div class="text-lg font-semibold">Why is SHIB surging?</div>
						<div class="mb-2 text-sm">
							SHIB is on the rise, everyone is getting crazy asldkasld alksdjlaksd jalksdjla jlaksdj
						</div>

						<div class="flex">
							<code class="mr-5 code"> Today in Market </code>

							<div class="text-xs text-gray-500">2 weeks ago</div>
						</div>
					</div>

					<div class="">
						<div class="pb-5">
							<img
								src="/trending/shiba coin.png"
								alt="trending_image"
								class="object-cover object-top h-48 rounded-2xl w-96"
							/>
						</div>

						<div class="text-lg font-semibold">Why is SHIB surging?</div>
						<div class="mb-2 text-sm">
							SHIB is on the rise, everyone is getting crazy asldkasld alksdjlaksd jalksdjla jlaksdj
						</div>

						<div class="flex">
							<code class="mr-5 code"> Analysis </code>

							<div class="text-xs text-gray-500">2 weeks ago</div>
						</div>
					</div>

					<div>
						<div class="pb-5">
							<img
								src="/trending/bitcoin rising.png"
								alt="trending_image"
								class="object-cover h-48 rounded-2xl w-96"
							/>
						</div>

						<div class="text-lg font-semibold">Why is SHIB surging?</div>
						<div class="mb-2 text-sm">
							SHIB is on the rise, everyone is getting crazy asldkasld alksdjlaksd jalksdjla jlaksdj
						</div>

						<div class="flex">
							<code class="mr-5 code"> Analysis </code>

							<div class="text-xs text-gray-500">2 weeks ago</div>
						</div>
					</div>
				</div>
			</div>
		{:else}
		<div class='h-[100px]'>
			
		</div>
		{/if}
	</div>
</IntersectionObserver>
