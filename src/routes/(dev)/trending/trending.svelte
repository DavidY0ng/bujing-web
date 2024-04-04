<script lang='ts'>
    import IntersectionObserver from "svelte-intersection-observer"
    import { fly } from "svelte/transition"
    import activity_data from './activity-data.json'
    import Carousel from 'svelte-carousel';
    import { browser } from '$app/environment';
    
    let node: any
</script>
<IntersectionObserver element={node} let:intersecting once >
    <div bind:this={node}>
    {#if intersecting}
        <div transition:fly={{ y:50, duration:1200, delay:200}}>
            <div class="mb-8 font-bold text-center h2">
                过去活动
            </div>
            <Carousel
                particlesToShow={4}
                particlesToScroll={1}
                dots={false}
               >
            <!-- <div class="grid grid-cols-4 gap-4 " > -->
                {#if browser}
                
                    {#each activity_data as data}
                    <a class="" href={data.href}  target='_blank'>
                        <div class="pb-5 mx-2">
                            <img src='/pastActivity/{data.img}' alt='trending_image' class="object-cover h-48 rounded-2xl w-96">
                        </div>

                        <div class="flex mb-2">
                            <!-- <code class="mr-5 code">
                                Analysis
                            </code> -->
                
                            <div class="mx-2 text-xs text-gray-500">
                                {data.date}
                            </div>
                        </div>
                        
                        <div class="mx-2 mb-2 text-lg font-semibold">
                        {data.title}
                        </div>
                        <div class="mx-2 mb-2 text-sm text-gray-300">
                            {data.description}
                        </div>
                    </a>
                    {/each}
                {/if}
                
            <!-- </div> -->
            </Carousel>
                

        </div>
    {/if}
</div>
</IntersectionObserver>