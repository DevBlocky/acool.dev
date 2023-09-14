<script lang="ts">
	export let title: string;
	export let badgeLabels: string[];
</script>

<div>
	<div class="inline-block border-l border-b border-black pb-2 pl-2">
		<div class="font-bold">{title}</div>
		<div class="flex justify-center divide-x text-sm">
			{#each badgeLabels as badge}
				<div class="px-2">{badge}</div>
			{/each}
		</div>
	</div>
</div>
