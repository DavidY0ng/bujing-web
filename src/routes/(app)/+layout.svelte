<script lang="ts">
    import { AppShell } from '@skeletonlabs/skeleton';
    import TopNav from '$lib/components/topNav/topNav.svelte';
    import Footer from '$lib/components/footer/footer.svelte';
    import { browser } from '$app/environment';
    import {onMount, onDestroy} from 'svelte'


    const scrollNavBar = 600
	let show = false

	function onScroll(e) {
		if (e.target.scrollTop > scrollNavBar) {
            show = true
        } else {
            show = false
        }
	}

</script>

<!-- <svelte:body bind:this={shell} /> -->
<AppShell  on:scroll={onScroll}>
    <svelte:fragment slot="header">
        <nav class="{show? "scrolled": ""}">
            <TopNav />

        </nav>

    </svelte:fragment>
    <!-- (sidebarLeft) -->
    <!-- (sidebarRight) -->
    <!-- (pageHeader) -->
    <!-- Router Slot -->
    <div class="pt-[80px]">
        <slot />
    </div>

    <!-- <div class="max-w-[1400px] p-7">
        <slot />
    </div> -->
    
    
    <!-- ---- / ---- -->
    <svelte:fragment slot="pageFooter">
        <Footer />
    </svelte:fragment>
    <!-- (footer) -->

</AppShell>

<style>
    .scrolled {
      transform: translate(0,calc(-100% - 5rem));
      opacity: 0
    }

    nav {
		transition: 0.5s ease
		
	}


  </style>