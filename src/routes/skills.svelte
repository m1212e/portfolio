<script lang="ts">
	import Switch from '../lib/switch.svelte';
	import JsLogo from '../images/javascript-logo.png';
	import ExpressJSLogo from '../images/expressjs-logo.svg';
	import FirebaseLogo from '../images/firebase-logo.svg';
	import SvelteLogo from '../images/svelte-logo.svg';
	import CypressLogo from '../images/cypress-logo.png';
	import AngularLogo from '../images/angular-logo.svg';
	import PuppeteerLogo from '../images/puppeteer-logo.png';
	import SocketioLogo from '../images/socketio-logo.svg';
	import PrismaLogo from '../images/prisma-logo.svg';
	import NPMLogo from '../images/npm-logo.svg';
	import ESLintLogo from '../images/eslint-logo.svg';
	import Skill from '../lib/skills/skill.svelte';

	const languages = [
		{
			name: 'JavaScript',
			icon: JsLogo,
			text: 'In the first semesters of university, JS was one of the languages taught. As THE langauge of the web, I learned the basics in combination with HTML and CSS and built a few Websites from scratch. During the pandemic I spent a lot of time learning JS, not only in the web but also with runtimes like Node.js and frameworks like Express. JS is one of the languages I know best and I am always looking for new ways to improve my skills in the JS ecosystem.'
		}
	];

	const frameworks = [
		{
			name: 'Express.js',
			icon: ExpressJSLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript']
		},
		{
			name: 'Firebase',
			icon: FirebaseLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Svelte',
			icon: SvelteLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Cypress',
			icon: CypressLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript']
		},
		{
			name: 'Angular',
			icon: AngularLogo,
			text: 'Lorem Ipsum',
			languages: ['typescript']
		},
		{
			name: 'Puppeteer',
			icon: PuppeteerLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Socket.io',
			icon: SocketioLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Prisma',
			icon: PrismaLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'npm',
			icon: NPMLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'ESLint',
			icon: ESLintLogo,
			text: 'Lorem Ipsum',
			languages: ['javascript', 'typescript']
		}
	];

	let checked = false;
</script>

<div class="flex w-100 justify-between mb-8">
	<div>
		<h1 id="career" class="font-bold text-4xl">Skills</h1>
		<p>On the right side of each entry you can see associated tools that I also worked with.</p>
	</div>
	<div class="flex items-center">
		<p class="font-semibold text-2xl mr-3 pb-1" class:underline={!checked}>Language</p>
		<Switch bind:checked />
		<p class="font-semibold text-2xl ml-3 pb-1" class:underline={checked}>Framework</p>
	</div>
</div>

{#each languages as lang}
	<Skill {lang} {frameworks} />
{/each}
