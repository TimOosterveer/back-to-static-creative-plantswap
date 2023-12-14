<div class="moon">
	<img src="https://hermenegildacode.github.io/theUniverse/img/moon.png" alt="" />
</div>

<style>
	.moon {
		position: absolute;
		top: 10rem;
		left: 30%;
		z-index: -2;
		width: 50%;
		height: 0px;
		animation: moon 30s linear infinite;
		transform-origin: 50%;
	}

	.moon img {
		object-fit: contain;
		width: 10%;
	}

	@keyframes moon {
		from {
			transform: rotate(0deg);
			scale: 1.5;
		}
		to {
			transform: rotate(360deg);
		}
	}
</style>
