<script>
	import '../app.postcss';
	import '../fonts.css';
	import Nav from './nav.svelte';
</script>

<div class="flex grow justify-between max-w-7xl pt-28 px-4">
	<div>
		<slot />
	</div>
	<Nav />
</div>

<style>
	:root {
		display: flex;
		justify-content: center;
		@apply sm:pr-56
	}
</style>
