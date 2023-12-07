<script>
	export let data;
	import Home from './home/+page.svelte';
	import NavDark from '$lib/organisms/NavDark.svelte';
	import Footer from '$lib/organisms/Footer.svelte';
	import MobileMenu from '$lib/organisms/MobileMenu.svelte';
</script>


<div>
	
</div>

<NavDark />
<MobileMenu />
<Home {data} />

<Footer />

