<script>
	import { gsap } from 'gsap';
	import { onMount } from 'svelte';
	import mountain from '$lib/assets/mountainscreative.png'

	onMount(() => {
		let menuButton = document.querySelector('.menu-button');
		let mm = gsap.matchMedia();

		let tl = gsap.timeline({ paused: true, reversed: true });
		tl.to('.menu-wrapper', {
			width: '100%',
			borderRadius: '0em',
			duration: 1.2,
			ease: 'Expo.easeInOut'
		});

		mm.add('(max-width: 700px)', () => {
			tl.to(
				'.menu-wrapper',
				{
					width: '100%',
					borderRadius: '0em',
					duration: 1.2,
					ease: 'Expo.easeInOut',
					delay: 0
				},
				'<'
			);
		});

		tl.to('.menu-button', { opacity: 0, duration: 0.001, ease: 'Expo.easeInOut', delay: 0 }, '<');
		'.close-button', { opacity: 1, duration: 0.001, ease: 'Expo.easeInOut', delay: 1 }, '<';
		tl.to(
			'.menu-wrapper',
			{
				height: '100svh',
				opacity: 1,
				duration: 1.2,
				ease: 'Expo.easeOut',
				delay: 0.1,
				y: '0'
			},
			'<'
		);
		tl.to(
			'button img',
			{ rotate: 360, x: -6, duration: 1.5, ease: 'Expo.easeInOut', delay: 0 },
			'<'
		);
		tl.to('.menu-text-gsap', { y: 0, duration: 2, ease: 'Expo.easeOut', delay: 0.6 }, '<');
		tl.to('.number', { y: 0, duration: 1.7, ease: 'Expo.easeOut' }, '<');
		tl.to(
			'.socials-gsap',
			{ y: 0, duration: 1.5, stagger: 0.2, delay: 0.4, ease: 'Expo.easeInOut' },
			'<'
		);

		menuButton.addEventListener('click', function () {
			if (tl.reversed()) {
				tl.timeScale(1.5).play();
			} else {
				tl.timeScale(1.5).reverse();
			}
		});
		console.log(menuButton)

		const home = document.getElementById('home');
	});
</script>

<section>
	<button class="menu-button">
		<svg width="17" height="16" viewBox="0 0 17 16" fill="none" xmlns="http://www.w3.org/2000/svg">
			<line y1="1" x2="17" y2="1" stroke="" stroke-width="2" />
			<line y1="7.61133" x2="17" y2="7.61133" stroke="" stroke-width="2" />
			<line y1="14.2222" x2="17" y2="14.2222" stroke="" stroke-width="2" />
		</svg>
	</button>
	<div class="menu-wrapper">
		<!-- <div class="background-image">
			<img src="https://cdn.dribbble.com/userupload/4959750/file/original-96d0e2eacf9f93da434671fb03f7540d.png?resize=1200x900" alt="">
		</div> -->

		<div class="space stars1"></div>
		<div class="space stars2"></div>
		<div class="space stars3"></div>
		<div class="earth">
			<img src="https://hermenegildacode.github.io/theUniverse/img/world.png" alt="" />;
		</div>

		<div class="moon">
			<img src="https://hermenegildacode.github.io/theUniverse/img/moon.png" alt="" />
		</div>

		<div class="mountains">
			<img src={mountain} alt="">
		</div>

		<button class="close-button">
			<svg width="15" height="15" viewBox="0 0 15 15" fill="" xmlns="http://www.w3.org/2000/svg">
				<line x1="1.19685" y1="1.29289" x2="13.2177" y2="13.3137" stroke="" stroke-width="2" />
				<line x1="1.29289" y1="13.3139" x2="13.3137" y2="1.29307" stroke="" stroke-width="2" />
			</svg>
		</button>
		<nav>
			<ul>
				<li>
					<a class="menu-text-gsap" id="home" href="/">Home</a>
				</li>
				<li>
					<a class="menu-text-gsap" id="stekjes" href="/stekjes_overzicht  ">Stekjes</a>
				</li>
				<li>
					<a class="menu-text-gsap" id="workshops" href="/workshops">Workshops</a>
				</li>
				<li>
					<a class="menu-text-gsap contact-link" id="dekast" href="/maken">De Kast</a>
				</li>
				<li>
					<a class="menu-text-gsap contact-link" id="contact" href="/contact">Contact</a>
				</li>
			</ul>
		</nav>
	</div>
</section>

<style>
	.menu-wrapper {
		position: fixed;
		right: 0;
		top: 0;
		height: 0px;
		width: 100%;
		display: flex;
		flex-direction: column;
		/* background-color: darkblue; */
		/* background-image: url(https://cdn.dribbble.com/userupload/7529706/file/original-7803eb8d07c27a1995de6601b1cb71e0.png?resize=1200x900);
		background-size: cover; */
		/* padding: 1.1em; */
		background: radial-gradient(circle at bottom, navy 0, black 100%);
		overflow: hidden;
		z-index: 1000;
		overflow: hidden;
		opacity: 1;
		transform: translateY(-3em);
		z-index: 999999;
	}

	.space {
		background: rgba(128, 0, 128, 0.1) center / 200px 200px round;
		bottom: 0;
		left: 0;
		position: absolute;
		right: 0;
		top: 0;
		z-index: -2;
	}

	.stars1 {
		animation: space 18s ease-in-out infinite;
		background-image: radial-gradient(1px 1px at 25px 5px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1px 1px at 50px 25px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1px 1px at 125px 20px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1.5px 1.5px at 50px 75px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2px 2px at 15px 125px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2.5px 2.5px at 110px 80px, white, rgba(255, 255, 255, 0));
	}

	.stars2 {
		animation: space 24s ease-in-out infinite;
		background-image: radial-gradient(1px 1px at 75px 125px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1px 1px at 100px 75px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1.5px 1.5px at 199px 100px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2px 2px at 20px 50px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2.5px 2.5px at 100px 5px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2.5px 2.5px at 5px 5px, white, rgba(255, 255, 255, 0));
	}

	.stars3 {
		animation: space 30s ease-in-out infinite;
		background-image: radial-gradient(1px 1px at 10px 10px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1px 1px at 150px 150px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1.5px 1.5px at 60px 170px, white, rgba(255, 255, 255, 0)),
			radial-gradient(1.5px 1.5px at 175px 180px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2px 2px at 195px 95px, white, rgba(255, 255, 255, 0)),
			radial-gradient(2.5px 2.5px at 95px 145px, white, rgba(255, 255, 255, 0));
	}

	.mountains {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
	}
	.mountains img {
		width: 100%;
	}

	@keyframes space {
		40% {
			opacity: 0.75;
		}
		50% {
			opacity: 0.25;
		}
		60% {
			opacity: 0.75;
		}
		100% {
			transform: rotate(360deg);
		}
	}
	/* .background-image {
		position: absolute;
		width: 100%;
		height: 100%;
		padding: 0;
		z-index: -3;
	}

	.background-image img {
		width: 100%;
		height: 100%;
	}

	.background-image::after {
		content: '';
		background-color: rgba(0, 0, 0, 0.533);
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	} */

	.menu-button {
		position: fixed;
		display: none;
		top: 1.5em;
		right: 1em;
		background-color: #ffffff00;
		border: 0;
		transition: transform 0.2s;
		padding: 1em;
		transform: scale(1.2);
		stroke: var(--background-color-light);
		z-index: 999999;
	}

	.earth {
		position: absolute;
		top: 10rem;
		left: 40%;
		z-index: -1;
		width: 100%;
		height: 0px;
	}

	.earth img {
		object-fit: contain;
		width: 10%;
		animation: earth 120s linear infinite;
	}

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

	.close-button {
		stroke: var(--background-color);
		position: fixed;
		top: 1.5em;
		right: 1em;
		opacity: 1;
		z-index: 2000;
		border: 0;
		background-color: #ffffff00;
		transform: scale(1.1);
		padding: 1em;
	}

	nav li {
		list-style-type: none;
		display: flex;
		flex-direction: row;
		gap: 1em;
		align-items: baseline;
		clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
	}

	p {
		color: var(--background-color);
		font-size: 1em;
	}

	a {
		text-decoration: none;
		color: white;
		z-index: 5;
	}
	nav a {
		font-size: 5em;
		transform: translateY(-130%);
		transition: margin 0.2s;
	}

	svg {
		pointer-events: none;
	}

	@media screen and (max-width: 1122px) {
	}

	@media screen and (max-width: 200000px) {
		.menu-wrapper {
			top: 0;
			right: 0;
			display: block;
		}

		.menu-button {
			display: block;
		}

		/* nav {
			margin-top: 1%;
		} */

		nav a {
			margin-top: 3%;
			font-size: 10vw;
		}

		.menu-button {
			z-index: 2000;
		}

		.close-button {
			z-index: 2000;
		}
	}

	@keyframes earth {
		0% {
			rotate: 0deg;
			scale: 1;
		}

		50% {
			rotate: 180deg;
			scale: 1.8;
		}

		100% {
			rotate: 360deg;
			scale: 1;
		}
	}

	@keyframes moon {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(360deg);
		}
	}
</style>
