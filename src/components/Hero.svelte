<script lang="ts">
	let className: string;
	export { className as class };
</script>

<div class="{className} space-y-6 p-4 md:p-8 hero">
	<h1 class="font-bold text-5xl md:text-6xl underline">Welcome.</h1>
	<p class="text-lg leading-loose">
		When good isn't good enough, Jacob delivers <b>excellence</b>.
	</p>

	<div>
		<blockquote class="italic">
			"Software and cathedrals are much the same &mdash; first we build them, then we pray"
		</blockquote>
		<div class="font-semibold ml-6">- Sam Redwine Jr.</div>
	</div>
</div>

<style lang="scss">
	$border-sz: 110px;
	.hero {
		@apply relative;
	}
	// top left border
	.hero::before {
		content: '';
		@apply absolute top-0 left-0 border-white border-t-2 border-l-2;
		width: $border-sz;
		height: $border-sz;
	}
	// bottom right border
	.hero::after {
		content: '';
		@apply absolute bottom-0 right-0 border-white border-b-2 border-r-2;
		width: $border-sz;
		height: $border-sz;
	}
</style>
