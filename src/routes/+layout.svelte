<script context="module">
	import './+layout.scss';
</script>

<svelte:head>
	<title>acool.dev</title>

	<!-- Google tag (gtag.js) -->
	<!-- Google tag (gtag.js) -->
	<script async src="https://www.googletagmanager.com/gtag/js?id=G-5WY6DZ0FFJ"></script>
	<script>
		window.dataLayer = window.dataLayer || [];
		function gtag() {
			dataLayer.push(arguments);
		}
		gtag('js', new Date());

		gtag('config', 'G-5WY6DZ0FFJ');
	</script>
</svelte:head>

<slot />
