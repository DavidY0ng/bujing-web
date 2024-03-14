<script>
    import { AppShell } from '@skeletonlabs/skeleton';
    import TopNav from '$lib/components/topNav/topNav.svelte';
    import Footer from '$lib/components/footer/footer.svelte';
</script>

<AppShell slotHeader="">
	<svelte:fragment slot="header">
        <div class="">
            <TopNav />
        </div>
        
    </svelte:fragment>
	<!-- (sidebarLeft) -->
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
    <div class="">
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