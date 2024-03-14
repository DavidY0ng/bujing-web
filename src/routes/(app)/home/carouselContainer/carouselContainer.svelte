<script lang='ts'>
    // import { AppShell } from '@skeletonlabs/skeleton';
    import Icon from '@iconify/svelte';
    import IntersectionObserver from "svelte-intersection-observer"
    import { fly } from "svelte/transition"
    import { fade } from 'svelte/transition';
    import Carousel from 'svelte-carousel';
    import { browser } from '$app/environment';

    let node:any;
    const socialImg = [1,2,3,4,5,6,7]
    const articleInfos = [
        {
            img: "1",
            title: "CRYPTO ON THE RISE",
            subtitle: "Understanding crypto bull market.",
            author: "David Hoffman",
            day: "1 day ago"
        },
        {
            img: "2",
            title: "CRYPTO ON THE RISE",
            subtitle: "hello",
            author: "William Pester",
            day: "1 day ago"
        },
        {
            img: "3",
            title: "Why buy",
            subtitle: "hello",
            author: "David Hoffman",
            day: "1 day ago"
        }
    ]

    const latestInfos = [
        {
            title: "金色电音节",
            category: "活动",
            time: '3月23日',
            href:'https://twitter.com/bujingmalaysia/status/1767513240081490019',
            signup: 'https://jinse.cn/blockchain/3677157.html'
        },
        {
            title: "Bitcoin's $70,000 Question",
            category: "TODAY IN MARKETS",
            time: '1 day ago'
        },
        {
            title: "When will Altcoin Season Arrive?",
            category: "ANALYSIS",
            time: '2 days ago'
        },
        {
            title: "When will Altcoin Season Arrive?",
            category: "ANALYSIS",
            time: '2 days ago'
        }
    ]

    const enlarge = () => {
        
    }
					             
</script>

<div class="flex gap-5">
    <div class="w-[75%]">
        {#if browser}
            <Carousel 
                arrows={false} 
                autoplay={true}
                pauseOnFocus = {true}>
            {#each socialImg as img}
            <div class="">
                    <div class="flex justify-center rounded-xl">
                        <img 
                        src="/social/{img}.jpeg" 
                        alt='social {img}'
                        class="object-contain w-[1100px] h-[500px] rounded-xl">
                    </div>
                    
                <!-- <div class="p-4 max-w-500px">
                    <div class="mb-2 font-bold h1">
                        {info.title}
                    </div>
                    <div class="mb-4 h3">
                        {info.subtitle}
                    </div>
                    <div class="flex mb-3 text-sm">
                        <div class="pr-3">
                            {info.author}
                        </div>
                        <div class="text-gray-400">
                            {info.day}
                        </div>
                    </div>
                    <button class="font-semibold text-black transition bg-white btn hover:bg-primary-500 hover:text-white">
                        READ ARTICLE
                    </button>
                    
                </div> -->
            </div>
            {/each}
            </Carousel>
        {/if}        
    </div>
    
    <div class="flex flex-col gap-4">
        <!-- latest news -->
        <div class="h-full p-4 border rounded-2xl border-secondary-800">
            <div class="mb-5 text-xl font-bold">
                <div class="h-[100px] w-[200px] mr-5 items-center flex ">
                    <img src='/logo/whale name.png' alt='bujing' class="">
                </div>
            </div>
            <IntersectionObserver element={node} let:intersecting once>
                <div bind:this={node} class="">
                    
                    <div class="flex flex-col gap-2"  >
                        <p class="text-lg font-semibold">
                            八卦 日常生活，了解各行各业的发展，关注币圈信息及知识
                        </p>
                    </div>
                   
                </div>
               
            </IntersectionObserver>
            <hr class="my-5">
            
            <div class="mb-5 text-gray-400">
                社交平台
            </div>

            <div class="flex justify-around w-[200px]">
				<a href='https://t.me/bujingpublic' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
						<Icon icon="mingcute:telegram-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
				
				<a href='https://twitter.com/bujingmalaysia' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
						<Icon icon="ri:twitter-x-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
				<a href='https://www.facebook.com/groups/bujing' target='blank'>
					<button class="p-2 bg-gray-700 rounded-full hover:variant-filled-secondary">
						<Icon icon="ri:facebook-fill" width="1.2em" height="1.2em" />
					</button>
				</a>
				
			</div>
            
        </div>
    
        <!-- sponsor -->
        <!-- <div class="p-4 border border-gray-800 rounded-2xl">
            <div class="mb-5 text-sm font-semibold text-gray-200">
                社交平台
            </div>
            <div class="flex items-center">
                <div class="h-[100px] w-[100px] mr-5 items-center flex">
                    <img src='/logo/whale.png' alt='bujing' class="w-40 rounded-full h-35">
                </div>
                <div>
                    <a href='#' class="anchor">BUJING</a>
                    <span>
                        - Empowered by BUJING society
                    </span>
                </div>
            </div>
        </div> -->

        
    </div>
    
    
</div>


<style>

</style>

