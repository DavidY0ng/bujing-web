<script lang="ts">
	import Icon from '@iconify/svelte';
	import { onDestroy, onMount } from 'svelte';
	import Typed from 'typed.js';
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fly } from 'svelte/transition';

	let node: any;
	let textRef;
	let typed;

	onMount(() => {
		import('typed.js').then(({ default: Typed }) => {
			typed = new Typed('#typed', {
				strings: ['Updated', 'Connected', 'Engaged'],
				typeSpeed: 80,
				backSpeed: 80,
				backDelay: 2000,
				loop: true
			});
		});
	});
</script>

<!-- <div class="p-4 card bg-gradient-to-tb variant-soft-tertiary">
	<div class="flex items-center justify-between p-[100px]">
		<div>
			<div class="pb-4 font-bold h1">
				Stay 
                <span id='typed' class="typed text-primary-500"></span>
            </div>
			<div>
				Join the world's most popular crypto community with daily alpha, news, & analysis for FREE.
			</div>
		</div>

		<div>
			<div class="mb-3 font-bold h3">Get connected</div>
			<div class="flex justify-around">
				<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
					<Icon icon="mingcute:telegram-fill" width="1.2em" height="1.2em" />
				</button>
				<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
					<Icon icon="ri:twitter-fill" width="1.2em" height="1.2em" />
				</button>
				<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
					<Icon icon="ri:instagram-fill" width="1.2em" height="1.2em" />
				</button>
			</div>
		</div>
	</div>
</div> -->

<div class="bg-gradient-to-b from-surface-900 to-black">
	<div class="flex flex-col items-center p-[100px] py-[150px]">
		<div>
			<div class="pb-4 font-bold text-center h1 text-[80px]">
				Stay
				<i><span id="typed" class="typed text-primary-500"></span></i>
			</div>
		</div>

		<div class="mb-5 h3">Join the world's most popular crypto community.</div>

		<div>
			<div class="flex justify-around w-[200px]">
				<a href='https://t.me/bujingpublic' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
						<Icon icon="mingcute:telegram-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
				
				<a href='https://twitter.com/bujingmalaysia' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
						<Icon icon="ri:twitter-x-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
				<a href='https://www.facebook.com/groups/bujing' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-primary">
						<Icon icon="ri:facebook-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
			</div>
		</div>
	</div>
</div>

