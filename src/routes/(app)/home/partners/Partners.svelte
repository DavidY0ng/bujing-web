<script lang="ts">
	import Icon from "@iconify/svelte";

	let partnersData = [
		{
			img: '1.png',
			title: 'Bybit',
			description: '受邀用户专享福利！立即注册，领取高达30,000美元存款奖金。',
            href:'https://partner.bybitglobal.com/b/bujing'
		},
		{
			img: '2.png',
			title: 'BingX',
			description: '立即使用我们的推荐码注册，最高可领取5000美元的奖励。',
            href:'https://bingx.com/invite/QVCZIF'
		},
		{
			img: '3.png',
			title: 'Bitget',
			description: '在Bitget注册以获得最高 1,000 USDT 的奖金',
            href:'https://www.bitget.fit/zh-CN/register?channelCode=a1j3&vipCode=c3sq6972&groupId=332139'
		},
        {
			img: '4.png',
			title: 'Pionex',
			description: '立即注册、充值，并参与手动期货交易，最高可赢取2,125美元。',
            href:'https://www.pionex.com/signUp?r=bujingclub'
		}
	];
</script>
<div class="flex justify-center">
    <div class="max-w-[1400px] w-full md:pb-[150px] pt-[100px]">
        <div class="flex flex-col items-center">
            <div class="mb-10 font-bold h1">我们的合作伙伴</div>
            <div class="mb-10 text-center md:w-[70%] text-xl">
                我们的合作伙伴是我们的可靠盟友，与我们密切合作，共同实现共同目标，促进共同成长和创新。
            </div>
        </div>
       
    
        <div class="flex flex-col justify-center gap-5 md:flex-row">
            {#each partnersData as data}
                
                <div class="p-5 card hover:scale-105 lg:w-[25%] transition ">
                    <a href={data.href} target='blank'>
                        <div class="flex justify-center">
                            <img src="assets/img/partners/{data.img}" alt="1" class="h-[200px] w-[400px] mb-3 object-cover rounded-md" />
                        </div>
                        
    
                        <div class="flex flex-col justify-between h-[220px]">
                            <div class="">
                                <div class="mb-5 h3">
                                    {data.title}
                                </div>
                
                                <div class="text-gray-400">
                                    {data.description}
                                </div>
                            </div>

                            <div class="flex justify-end text-secondary-500">
                                <Icon icon="ic:round-link" width="1.8em" height="1.8em" />
                            </div>
                            
                        </div>
                        
    
                        
                    </a>
                    
                </div>
            {/each}
        </div>
    
    </div>
</div>

