<script>
	import Career from './career.svelte';
	import Home from './home.svelte';
	import Skills from './skills.svelte';
	import { base } from '$app/paths';
</script>

<Home />
<div class="my-36" />
<Career />
<div class="my-36" />
<!-- <div class="text-5xl my-10">!!!Logo Rechte checken ab node.js (inklusive)!!!</div> -->
<Skills />
<h1 id="showcase">Showcase</h1>

<div class="flex">
	<a class="mt-32 mr-10" href={base + '/imprint'}>Imprint/Impressum (German/Deutsch)</a>
	<a class="mt-32" href={base + '/privacy'}>Privacy/Datenschutz (German/Deutsch)</a>
</div>
