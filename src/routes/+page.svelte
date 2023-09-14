<script lang="ts">
	import Hero from '../components/Hero.svelte';
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import ProjectCard from '../components/ProjectCard.svelte';
	import type { Project } from '../components/ProjectCard.svelte';

	const showcase: Project[] = [
		{
			title: 'acool.dev',
			langs: ['TypeScript', 'HTML', 'SCSS'],
			technologies: ['Svelte', 'TailwindCSS'],
			desc: "Hey look, it's this website! Using Svelte, TailwindCSS, and Vite, acool.dev is a small single-page application that showcases some of my work",
			link: 'https://github.com/DevBlocky/acool.dev'
		},
		{
			title: 'Forceps',
			langs: ['Rust'],
			technologies: ['tokio', 'serde', 'sled'],
			desc: 'Made in Rust, forceps is a light and async disk database/cache that works as an alternative to projects like RocksDB',
			link: 'https://github.com/DevBlocky/forceps'
		},
		{
			title: 'Neopolitan UI',
			langs: ['Lua', 'JavaScript', 'HTML', 'CSS'],
			technologies: ['Vue', 'FiveM'],
			desc: 'Neopolitan UI (NeoUI for short) is a FiveM menu library meant as a CPU-light version of NativeUI and other native-based menus',
			link: 'https://github.com/DevBlocky/neo-ui'
		},
		{
			title: 'Pseudo Hilbert Curve',
			langs: ['C'],
			technologies: ['CMake'],
			desc: 'Calculates the coordinates of psuedo Hilbert curves, an iteration of the infinitely large Hilbert space-filling curve',
			link: 'https://github.com/DevBlocky/pseudo-hilbert-curve'
		},
		{
			title: "Conway's Game of Life",
			langs: ['C'],
			technologies: ['CMake'],
			desc: "My personal implementation of the famous Conway's Game of Life, displayed in the console for the user",
			link: 'https://github.com/DevBlocky/conway-gol'
		}
	];
</script>

<div
	class="min-h-screen flex flex-col overflow-hidden bg-gradient-to-tl from-sky-500 to-indigo-600"
>
	<div class="flex-1 font-raleway">
		<Header />

		<div
			class="grid grid-cols-1 md:grid-cols-2 gap-x-4 gap-y-8 md:gap-y-24 p-8 mt-8 md:mt-24 container mx-auto"
		>
			<div class="inverting-stripe">
				<Hero class="text-white" />
			</div>

			{#each showcase as proj}
				<ProjectCard {proj} />
			{/each}
		</div>
	</div>
	<Footer />
</div>

<style lang="scss">
	$start-rot: 20deg;
	$end-rot: 135deg;

	@keyframes stripe-rotate {
		0% {
			transform: rotate($start-rot);
		}
		100% {
			transform: rotate($end-rot);
		}
	}
	.inverting-stripe {
		position: relative;
	}
	.inverting-stripe::before {
		animation: stripe-rotate 1.9s;
		animation-timing-function: cubic-bezier(0.22, 0.61, 0.36, 1);
		transform: rotate($end-rot);

		position: absolute;
		z-index: 1000;
		pointer-events: none;

		content: '';
		background-color: white;
		mix-blend-mode: difference;

		top: 50%;
		left: 50%;
		height: 400vmax;
		margin-top: -200vmax;

		$w: 150px;
		width: $w;
		margin-left: calc($w / -2);
		// width: 15vmax;
		// margin-left: -7.5vmax;
	}
	@screen md {
		.inverting-stripe::before {
			$w: 300px;
			width: $w;
			margin-left: calc($w / -2);
		}
	}
</style>
