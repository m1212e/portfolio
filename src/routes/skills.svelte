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
	import TypeScriptLogo from '../images/typescript-logo.svg';
	import JavaLogo from '../images/java-duke-logo.svg';
	import CLogo from '../images/c-logo.svg';
	import CPPLogo from '../images/c++-logo.svg';
	import GoLogo from '../images/go-logo.svg';
	import RustLogo from '../images/rust-logo.svg';
	import TokioLogo from '../images/tokio-logo.svg';
	import ReactLogo from '../images/react-logo.svg';
	import Skill from '../lib/skills/skill.svelte';

	const languages = [
		{
			name: 'JavaScript',
			icon: JsLogo,
			text: 'In the first semesters of university, JS was one of the languages taught. As THE langauge of the web, I learned the basics in combination with HTML and CSS and built a few Websites from scratch. During the pandemic I spent a lot of time learning JS, not only in the web but also runtimes like Node.js and frameworks like Express. JS is one of the languages I know best and I am always looking for new ways to improve my skills in the JS ecosystem.'
		},
		{
			name: 'TypeScript',
			icon: TypeScriptLogo,
			text: "Soon after getting into the JavaScript ecosystem, I heard of TypeScript. Since I learned a few strongly typed languages before, I immediately knew which benefits TypeScript has and quickly got into learning it. Since it's very similar to JavaScript it wasn't a big hurdle and now almost every web project I work on uses the benefits and flexibility of TypeScript."
		},
		{
			name: 'Go',
			icon: GoLogo,
			text: "After developing in JS/TS for the major part of my university and side projects, I wanted to learn a faster, more low level, compiled language. Since Go is an easy to learn language, I picked it up for some side projects and wrote the web backend for my bachelors thesis, which focused around web app performance, with the Fiber framework. I worked with the standard libary a lot and got into testing soon after. I really enjoyed using Go for it's simplicity, large standard library and fast performance out of the box."
		},
		{
			name: 'Rust',
			icon: RustLogo,
			text: "While developing on a side project where I hit the limit of the used tools and languages I made the decision to take a look at Rust. Since it's a steep learning curve it took a few attempts for me to really click with the language but now I absolutely love it. To me the language design checks a lot of boxes and I enjoy writing it, even if the progress is noticeably slower than with other languages. On various projects I worked with the standard library, async Rust with Tokio, serde and a few web servers. I also used Rust to write my own parser."
		},
		{
			name: 'Java',
			icon: JavaLogo,
			text: 'As the first programming language I ever learned, Java has taught me the basics of programming. Starting out with writing plugins for Minecraft servers with the Bukkit API, I continued to develop some small applications with Swing. Later at university Java was taught to make us familiar with consepts like OOP and functional programming. After a pause I picked it up again at weiyu digital GmbH where I learned how to use the Spring framework, how to write tests and how to use Gradle as a build tool.'
		},
		{
			name: 'C++',
			icon: CPPLogo,
			text: 'In combination with the Qt GUI framework, C++ was taught at university. We wrote several GUI applications and made ourselves familiar with the C++ syntax. I even wrote a small "Battleships" game in Qt and C++. Although I don\'t use C++ very frequently, It\'s useful to know the language in various situations, e.g. with the Node.js native addon API.'
		},
		{
			name: 'C',
			icon: CLogo,
			text: "The first language I learned in university was C. It was a very interesting experience to learn a language that is so close to the machine. I learned how to use pointers and pointer arithmetics. Although I don't use C anymore, It taught me the basics and I still realize how much it helps to know a low level language like C."
		}
	];

	const frameworks = [
		{
			name: 'Express.js',
			icon: ExpressJSLogo,
			text: 'As one of the most used web backend frameworks for Node.js, Express was one of the first JS frameworks I got to know. I learned the concepts of a router, how middleware works and how to implement a template based web app. Throughout my projects I used Express to build a few small web APIs.',
			languages: ['javascript']
		},
		{
			name: 'Firebase',
			icon: FirebaseLogo,
			text: 'Through one of my favorite development YouTube channels Fireship I learned about Firebase. I really enjoyed the simplicity of the Firebase SDK and the ease of use of the Firebase CLI. I used Firebase to build a multiplayer card game and a native App for collecting and managing ideas and really enjoyed it\'s realtime features.',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Svelte',
			icon: SvelteLogo,
			text: 'Svelte was the third component frontend framework I learned. Since I already knew Angular and React I immediately realised how easy Svelte made the frontend development process. I picked it up really quickly and since then it is my framework of choice when it comes to web frontend development. I\'ve implemented a lot of projects with Svelte and SvelteKit, in fact, the site you\'re currently on is made with SvelteKit. It is the frontend framework I\'m the most familiar with.',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Cypress',
			icon: CypressLogo,
			text: 'During my time working as a fullstack developer at weiyu digital GmbH I learned about Cypress. I was tasked to write e2e tests for quite a big web app under time pressure. Before I suggested Cypress, the team used Protractor to write e2e tests for their apps. I had to convince the CTO of our customer and my boss to make the switch to Cypress. As it turned out, Cypress was the right tool for the choice and the tests could be implemented within the set deadline. I really enjoyed the tooling and extensive docs of Cypress.',
			languages: ['javascript']
		},
		{
			name: 'Angular',
			icon: AngularLogo,
			text: 'As the first Component frontend framework I learned, Angular taught me the basics of web development with a component based frontend framework. I learned how to use the Angular CLI, how to write components, how to use the Angular Material UI library and how client side routing works. Even though I don\'t use Angular anymore it was a good framework to learn the basics. During my time at weiyu digital GmbH I used Angular in a professional context.',
			languages: ['typescript']
		},
		{
			name: 'Puppeteer',
			icon: PuppeteerLogo,
			text: 'As one of the most flexible and capable tools when it comes to webscraping I used puppeteer in a few side projects which required not only the visit but also the automated interaction with web pages.',
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
			languages: ['typescript']
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
		},
		{
			name: 'Tokio',
			icon: TokioLogo,
			text: 'Lorem Ipsum',
			languages: ['rust']
		},
		{
			name: 'React',
			icon: ReactLogo,
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
	<div class="flex flex-col sm:flex-row items-center">
		<p class="font-semibold text-2xl mr-3 pb-1" class:underline={!checked}>Language</p>
		<Switch bind:checked />
		<p class="font-semibold text-2xl ml-3 pb-1" class:underline={checked}>Framework</p>
	</div>
</div>

{#if !checked}
	{#each languages as lang}
		<Skill
			item={lang}
			crossrefs={frameworks.filter((framework) =>
				framework.languages.find((l) => l.toLowerCase() == lang.name.toLowerCase())
			)}
			on:refClicked={(e) => {
				checked = true;
				setTimeout(() => {
					location.hash = '#' + e.detail.name;
				}, 50);
			}}
		/>
	{/each}
{:else}
	{#each frameworks as framework}
		<Skill
			item={framework}
			crossrefs={languages.filter((lang) =>
				framework.languages.find((l) => l.toLowerCase() == lang.name.toLowerCase())
			)}
			on:refClicked={(e) => {
				checked = false;
				setTimeout(() => {
					location.hash = '#' + e.detail.name;
				}, 50);
			}}
		/>
	{/each}
{/if}
