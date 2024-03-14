<script>
    import { LightSwitch } from '@skeletonlabs/skeleton';
    import { AppBar } from '@skeletonlabs/skeleton';
    import Icon from '@iconify/svelte';
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

<div class="sticky w-full shadow-md dark:bg-surface-800 bg-surface-100">
    <div class="max-w-[1400px] md:py-6 md:px-1 p-5 mx-auto">
        <div class="flex justify-between">
            <div class="flex">
                <a class="text-[25px] font-bold deciratuib-primary-500 mr-10" href='/home'>
                    <div class="md:h1 text-[35px]">
                        <span class="text-transparent bg-gradient-to-b from-secondary-500 to-tertiary-500 bg-clip-text box-decoration-clone">BUJING - 布鲸社区</span>
                    </div>
                </a>
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

            <div class="hidden md:flex">
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
                </div>
                
                <a href='https://t.me/bujingpublic' target='_blank'>
                    <button class="text-white shadow-md btn bg-gradient-to-br from-secondary-500 to-secondary-500">
                        加入电报群
                        <Icon icon="mingcute:telegram-line" width="1.2em" height="1.2em" class="ml-1"/>
                    </button>
                </a>
                
            </div>
            <div class="md:hidden">
                <Icon icon="mdi:hamburger-menu" width="1.5em" height="1.5em" />
            </div>
            
        </div>
        
    </div>
</div>


