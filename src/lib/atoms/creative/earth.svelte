<script>
	import clouds from '$lib/assets/clouds.png';
	import earth from '$lib/assets/earthone.png';
</script>

<div class="earth">
	<!-- <img id="one" src="https://hermenegildacode.github.io/theUniverse/img/world.png" alt="" />; -->
	<img id="one" src={earth} alt="" />
	<img id="two" src={clouds} alt="" />;
</div>

<style>
	.earth {
		position: absolute;
		top: 10rem;
		left: 40%;
		z-index: -1;
		width: 100%;
		height: 0px;
	}
	#one {
		object-fit: contain;
		width: 10%;
		animation: earth 120s linear infinite;
	}
	#two {
		position: absolute;
		top: 10rem;
		left: -190px;
		opacity: 0.7;
		width: 40%;
		animation: cloud 100s linear infinite;
	}

	@keyframes earth {
		0% {
			rotate: 0deg;
			scale: 1;
		}

		50% {
			rotate: 180deg;
			scale: 2.5;
		}

		100% {
			rotate: 360deg;
			scale: 1;
		}
	}

	@keyframes cloud {
		0% {
			rotate: 0;
			scale: 1;
		}

		30% {
			rotate: -60deg;
		}

		60% {
			rotate: 60deg;
			scale: 1.8;
		}

		100% {
			rotate: 0;
			scale: 1;
		}
	}
</style>
