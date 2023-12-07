<!-- <script>
  import imaga from '$lib/assets/stek1.jpg'
	import { fly } from 'svelte/transition';
	import { backIn, backInOut, backOut, bounceIn, bounceInOut, cubicIn, cubicInOut, elasticOut, sineIn } from 'svelte/easing';
	export let data;

	function flush(
		node,
		{ delay = 0, duration = 500, easing = backInOut } = {},
		{ direction = 'both' } = {}
	) {
		// const origin = {
		//   in: 'bottom left',
		//   out: 'bottom right',
		//   both: 'center center'
		// }

		return {
			delay,
			duration,
			easing,
			css: (t) => `
    scale: ${t};
    opacity: ${t};
    transform-origin: top center;
    `
		};
	}

  function loadIn(
		node,
		{ delay = 0, duration = 500, easing = backInOut } = {},
		{ direction = 'both' } = {}
	) {
		// const origin = {
		//   in: 'bottom left',
		//   out: 'bottom right',
		//   both: 'center center'
		// }

		return {
			delay,
			duration,
			easing,
			css: (t) => `
    scale: ${t};
    opacity: ${t};
    transform-origin: top center;
    `
		};
	}
</script> -->

<!-- {#key data.url}
	<div in:loadIn={{ duration: 1000 }} out:flush={{ duration: 2000, delay: 500 }}>
		<slot />
	</div>
{/key} -->

<script>
  import Viewtransition from "$lib/viewtransition.svelte";
</script>


<div class="app">

  <Viewtransition />
  <slot/>

</div>

