<script>
	import { LightSwitch } from '@skeletonlabs/skeleton';
	import { AppBar } from '@skeletonlabs/skeleton';
	import { scrollToSection } from '$lib/store/store';
	import Icon from '@iconify/svelte';
	import { goto } from '$app/navigation';
	import { writable } from 'svelte/store';
	import { onMount, onDestroy } from 'svelte';
	import { browser } from '$app/environment';

	function scrollToSectionHandler(id) {
		scrollToSection.set(id);
	}
</script>

<!-- <AppBar 
    shadow="shadow-md" 
    padding='p-7'>
    <svelte:fragment slot="lead">
        <a class="text-[25px] font-bold deciratuib-primary-500 mr-10" href='/home'>
            <h1 class="h1">
                <span class="text-transparent bg-gradient-to-br from-primary-500 to-secondary-500 bg-clip-text box-decoration-clone">.Deploy</span>
            </h1>
        </a>
        
    </svelte:fragment>
    <div class="flex justify-around w-[500px] ">
        <a href='#' class="hover:underline">
            ARTICLES
        </a>
        <a href='#' class="hover:underline">
            NEWSLETTER
        </a>
        <a href='#' class="hover:underline">
            EPISODES
        </a>
    </div>
    <svelte:fragment slot="trail">
        
        <button class="text-white shadow-md btn bg-gradient-to-br from-secondary-500 to-primary-500">
            Join for Free
        </button>
    </svelte:fragment>
    

</AppBar> -->

<div class="fixed w-full shadow-md dark:variant-glass-primary bg-surface-100">
	<div class="max-w-[1400px] md:py-2 md:px-1 p-3 mx-auto">
		<div class="flex justify-between">
			<div class="flex">
				<div class="text-[25px] font-bold mr-10">
					<div class="md:h1 text-[35px]">
						<div>
							<img src="assets/img/logo/whale name.png" alt="whale logo" class="h-[60px] w-[130px]" />
						</div>
					</div>
				</div>
				<!-- <div class="hidden md:flex justify-around w-[300px] items-center font-semibold">
                        <a href='#' class="hover:underline">
                            ARTICLES
                        </a>
                        <a href='#' class="hover:underline">
                            NEWSLETTER
                        </a>
                        <a href='#' class="hover:underline">
                            EPISODES
                        </a>
                    </div> -->
			</div>

			<div class="flex">
				<div class="flex items-center justify-end mr-3">
					<!-- <div class="mr-3">
                            <LightSwitch />
                        </div> -->

					<!-- <div class="input-group grid-cols-[auto_1fr_auto] bg-white border border-gray-200 dark:border-gray-700">
                            <div class="">
                                <Icon icon="ic:baseline-search" width="1.2em" height="1.2em" />
                            </div>
                            <input type="search" placeholder="Search" class="p-1" />
                        </div> -->
					<div class="flex justify-between md:w-[150px] gap-5 h3 font-bold">
						<!-- <a
							href="#past-events"
							class="hover-underline-animation"
							on:click|preventDefault={() => scrollToSectionHandler('past-events')}
						>
							<button class=""> 过去活动 </button>
						</a> -->

						<a
							href="#milestone"
							class="hover-underline-animation"
							on:click|preventDefault={() => scrollToSectionHandler('milestone')}
						>
							<button class=""> 旅程 </button>
						</a>

						<a
							href="#partners"
							class="hover-underline-animation"
							on:click|preventDefault={() => scrollToSectionHandler('partners')}
						>
							<button class=""> 伙伴 </button>
						</a>
					</div>
				</div>

				<!-- <a href='https://t.me/bujingpublic' target='_blank'>
                        <button class="text-white shadow-md btn bg-gradient-to-br from-secondary-500 to-secondary-500">
                            加入电报群
                            <Icon icon="mingcute:telegram-line" width="1.2em" height="1.2em" class="ml-1"/>
                        </button>
                    </a> -->
			</div>
			<!-- <div class="md:hidden">
				<Icon icon="mdi:hamburger-menu" width="1.5em" height="1.5em" />
			</div> -->
		</div>
	</div>
</div>

<style>
	.hover-underline-animation {
		display: inline-block;
		position: relative;
	}

	.hover-underline-animation::after {
		content: '';
		position: absolute;
		width: 100%;
		transform: scaleX(0);
		height: 2px;
		bottom: 0;
		left: 0;
		background-color: #0087ca;
		transform-origin: bottom;
		transition: transform 0.25s ease-out;
	}

	.hover-underline-animation:hover::after {
		transform: scaleX(1);
		transform-origin: bottom;
	}
</style>
