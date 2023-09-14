<script context="module" lang="ts">
	export interface Project {
		title: string;
		langs?: string[];
		technologies?: string[];
		desc: string;
		link: string;
	}
</script>

<script lang="ts">
	import GradientText from './design/GradientText.svelte';
	import Badges from './design/Badges.svelte';

	export let proj: Project;
</script>

<div class="flex flex-col bg-white p-4 space-y-4 drop-shadow-lg">
	<h2 class="text-4xl font-bold">
		<GradientText class="from-violet-500 to-fuchsia-500">
			{proj.title}
		</GradientText>
		{#if proj.title === 'acool.dev'}
			<span class="text-sm text-white">hi mom!</span>
		{/if}
	</h2>

	<div class="flex flex-wrap gap-2">
		{#if proj.langs}
			<Badges title={proj.langs.length > 1 ? 'Languages' : 'Language'} badgeLabels={proj.langs} />
		{/if}
		{#if proj.technologies}
			<Badges title="Technologies" badgeLabels={proj.technologies} />
		{/if}
	</div>

	<p class="text-lg block">
		{proj.desc}
	</p>

	<!-- spacer -->
	<div class="flex-1 flex flex-col justify-end">
		<div class="flex justify-end">
			<a
				href={proj.link}
				class="px-4 py-2 bg-blue-800 text-white font-semibold hover:bg-blue-600 hover:scale-110 transition-all delay-75"
			>
				View on GitHub
			</a>
		</div>
	</div>
</div>
