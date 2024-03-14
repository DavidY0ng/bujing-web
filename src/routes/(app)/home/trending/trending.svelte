<script lang='ts'>
    import IntersectionObserver from "svelte-intersection-observer"
    import { fly } from "svelte/transition"
    
    let node: any
</script>
<IntersectionObserver element={node} let:intersecting once >
    <div bind:this={node}>
    {#if intersecting}
        <div transition:fly={{ y:50, duration:1200, delay:200}}>
            <div class="mb-8 font-bold h2">
                过去活动
            </div>
            <div class="grid grid-cols-4 gap-4 " >
                
                <a class="" href='https://www.fx168news.com/article/541274'  target='_blank'>
                    <div class="pb-5">
                        <img src='/pastActivity/discuss web3.png' alt='trending_image' class="object-cover h-48 rounded-2xl w-96">
                    </div>

                    <div class="flex mb-2">
                        <!-- <code class="mr-5 code">
                            Analysis
                        </code> -->
            
                        <div class="text-xs text-gray-500">
                            2024-03-04
                        </div>
                    </div>
                    
                    <div class="mb-2 text-lg font-semibold">
                        DiscussWeb3和马来西亚区块链社区独家活动
                    </div>
                    <div class="mb-2 text-sm text-gray-300">
                        来自 DiscussWeb3 和马来西亚区块链社区的独家活动：“链条腾飞，龙年大吉祥”在Icon City 已圆满落幕！
                    </div>

                    
                    
                </a>

                <a href='https://m.jinse.cn/blockchain/3670778.html' target='_blank'>
                    <div class="pb-5">
                        <img src='/pastActivity/fire dao.jpeg' alt='trending_image' class="object-cover h-48 rounded-2xl w-96">
                    </div>

                    <div class="flex mb-2">
                        <!-- <code class="mr-5 code">
                            Analysis
                        </code> -->
            
                        <div class="text-xs text-gray-500">
                            2023-12-26
                        </div>
                    </div>
                    
                    <div class="mb-2 text-lg font-semibold">
                        FireDAO Web3圣诞交流聚会回顾
                    </div>
                    <div class="mb-2 text-sm text-gray-300">
                        FireDAO于12月22日在The Earth Pavilion成功地举办了Web3圣诞交流聚会，活动在欢声笑语中完美落幕。大会衷心感谢合作社区与媒体的大力支持，为本次活动增添了丰富多彩的色彩。
                    </div>

                    
                    
                </a>

                <a href='https://m.jinse.cn/blockchain/3662830.html' target='_blank'>
                    <div class="pb-5">
                        <img src='/pastActivity/web3_mdec.jpeg' alt='trending_image' class="object-cover object-top h-48 rounded-2xl w-96">
                    </div>

                    <div class="flex mb-2">
                        <!-- <code class="mr-5 code">
                            Analysis
                        </code> -->
            
                        <div class="text-xs text-gray-500">
                            2023-10-19
                        </div>
                    </div>
                    
                    <div class="mb-2 text-lg font-semibold">
                        数字化未来：探索Web3.0与MDEC数字生态系统
                    </div>
                    <div class="mb-2 text-sm text-gray-300">
                        马六甲将成为全国首个引领各领域数位生态系统发展的智慧州属，积极迈向数字化未来。
                    </div>

                    
                    
                </a>

                <a href='https://www.coinlive.com/zh/news/discussweb3-org-the-first-web3-debate-was-grandly-opened-in-malaysia' target='_blank'>
                    <div class="pb-5">
                        <img src='/pastActivity/discuss web3 dec.jpg' alt='trending_image' class="h-48 object-fit rounded-2xl w-96">
                    </div>

                    <div class="flex mb-2">
                        <!-- <code class="mr-5 code">
                            Analysis
                        </code> -->
            
                        <div class="text-xs text-gray-500">
                            2023-12-9
                        </div>
                    </div>
                    
                    <div class="mb-2 text-lg font-semibold">
                        DiscussWeb3.org 首届Web3辩论会在马来西亚隆重开幕
                    </div>
                    <div class="mb-2 text-sm text-gray-300">
                        由Discussweb3.org主办，各社区协办的DiscussWeb3.org首届辩论会将于2023年12月9日在马来西亚吉隆坡FireDao Community Service Centre隆重开幕。
                    </div>

                    
                    
                </a>
                
            </div>
        </div>
    {/if}
</div>
</IntersectionObserver>