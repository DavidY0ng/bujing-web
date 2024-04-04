<script lang="ts">
	import Icon from '@iconify/svelte';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';

	let node: any;
</script>

<div class="w-full bg-black">
	<div class="p-[200px] bg-local bg-cover bg-[url('/assets/img/claimable/claimable_backdrop.jpg')]">
		<div class="flex flex-col items-center">
			<div class="h1 text-[80px] p-10">
				<IntersectionObserver element={node} let:intersecting once>
					<div bind:this={node}>
						{#if intersecting}
							<div transition:fly={{ y: 50, duration: 1200, delay: 500 }}>
								<i>Find</i> <span class="font-bold">YOUR</span> <i>Claimables</i>
							</div>
						{/if}
					</div>
				</IntersectionObserver>
			</div>

			<IntersectionObserver element={node} let:intersecting once>
				<div bind:this={node}>
					{#if intersecting}
						<div transition:fly={{ y: 50, duration: 1200, delay: 100 }}>
							<div class="mb-10 h2">Search or connect your wallets</div>
						</div>
					{/if}
				</div>
			</IntersectionObserver>
			<div
				class="border-none input-group grid-cols-[auto_1fr_auto] w-[500px] dark:bg-white"
			>
				<div class="text-gray-500 border-none">
					<Icon icon="material-symbols:search" width="1.2em" height="1.2em" />
				</div>
				<input class="p-3 text-gray-900" type="search" placeholder="Wallet address..." />
				<button class="variant-filled-primary">Search</button>
			</div>
		</div>
	</div>
</div>
