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
	import FiberLogo from '../images/fiber-logo.svg';
	import GORMLogo from '../images/GORM-logo.svg';
	import PostgresLogo from '../images/postgres-logo.svg';
	import GCPLogo from '../images/gcp-logo.svg';
	import GitHubLogo from '../icons/dark-github.svg';
	import NodejsLogo from '../images/nodejs-logo.svg';
	import SpigotLogo from '../images/spigot-logo.png';
	import SelfhostedLogo from '../images/selfhosted.svg';
	import ProtractorLogo from '../images/protractor-logo.svg';
	import gRPCLogo from '../images/grpc-logo.svg';
	import PWALogo from '../images/pwa-logo.svg';
	import TailwindLogo from '../images/tailwindcss-logo.svg';
	import DirectusLogo from '../images/directus-logo.svg';
	import NapirsLogo from '../images/napirs-logo.png';
	import LSPLogo from '../images/lsp-logo.svg';
	import MQTTLogo from '../images/mqtt-logo.svg';
	import ElectronLogo from '../images/electron-logo.svg';
	import Skill from '../lib/skills/skill.svelte';

	//TODO: I really like umformulieren

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
	].sort((a, b) => a.name.localeCompare(b.name));

	const tools = [
		{
			name: 'Express.js',
			icon: ExpressJSLogo,
			text: 'As one of the most used web backend frameworks for Node.js, Express was one of the first JS frameworks I got to know. I learned the concepts of a router, how middleware works and how to implement a template based web app. Throughout my projects I used Express to build a few small web APIs.',
			languages: ['javascript']
		},
		{
			name: 'Firebase',
			icon: FirebaseLogo,
			text: "Through one of my favorite development YouTube channels Fireship I learned about Firebase. I really enjoyed the simplicity of the Firebase SDK and the ease of use of the Firebase CLI. I used Firebase to build a multiplayer card game and a native App for collecting and managing ideas and found it's realtime features to be very useful.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Svelte',
			icon: SvelteLogo,
			text: "Svelte was the third component frontend framework I learned. Since I already knew Angular and React I immediately realised how easy Svelte made the frontend development process. I picked it up really quickly and since then it is my framework of choice when it comes to web frontend development. I've implemented a lot of projects with Svelte and SvelteKit, in fact, the site you're currently on is made with SvelteKit. It is the frontend framework I'm the most familiar with. Especially the SSG/SSR capabilities of SvelteKit are really useful and I'm looking forward to see where this trend and the framework is going to go.",
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
			text: "As the first Component frontend framework I learned, Angular taught me the basics of web development with a component based frontend framework. I learned how to use the Angular CLI, how to write components, how to use the Angular Material UI library and how client side routing works. Even though I don't use Angular anymore it was a good framework to learn the basics. During my time at weiyu digital GmbH I used Angular in a professional context.",
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
			text: 'For various small projects and a web based game I developed I used Socket.io to implement realtime communication between the client and the server. The ease of use, fallback mechanisms and extra features like rooms make it a very enjoyable tool to use whenever it comes to realtime apps.',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Prisma',
			icon: PrismaLogo,
			text: "For a small side projects which required a database I used Prisma. Even though I didn't dug too deep into it I found the readability of the schema and the resulting type safety very enjoyable to use and had a good developer experience.",
			languages: ['typescript']
		},
		{
			name: 'npm',
			icon: NPMLogo,
			text: "When it comes to dependency and project management in the web world there is no way around npm. As the first package manager I actually got to know well I quickly enjoyed the ease of use, the CLI and standardised way of structuring project dependencies. Although there are alternatives like pnpm, which are faster, npm provides super useful features and I highly appreciate it's simplicity. I've used it in countless projects.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'ESLint',
			icon: ESLintLogo,
			text: "In combination with Prettier as a code formatter I use ESLint to enforce a consistent code style in almost all of my projects. I really enjoy the flexibility of ESLint and hat it can be configured to fit the needs of almost any project. As I experienced it's often worth to take some time to configure it properly, because the time saved during development is almost always more than the setup took.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Tokio',
			icon: TokioLogo,
			text: "When it comes to async Rust, Tokio is the moste used and most popular runtime. Therefore when I learned async Rust I encountered Tokio along the way. I initially found async Rust and Tokio hard to learn, but after digging into it I really liked working with it since it abstracts away the really tough parts of writing an async program. I've used Tokio in a few projects already and are very happy with its features and performance. Coming from Go I especially like the Tokio channels for passing data between async contexts.",
			languages: ['rust']
		},
		{
			name: 'React',
			icon: ReactLogo,
			text: 'As it is the most popular component framework I learned React while implementing a few side and university projects. I liked the huge ecosystem and community that comes with React, which make it very easy to get going. I also worked on a React Native project with Expo during university, it was impressive how easy it is to develop an application for multiple platforms with the same tool.',
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Fiber',
			icon: FiberLogo,
			text: 'While researching tools for writing web servers with high performance I came across Fiber. It is a very high performance web framework for Go, which resembles Express.js. I used it in my bachelors thesis to implement a fast web api and found it to be a very enjoyable tool to use. It is very easy to get started with and provides a lot of features and ready to use middleware out of the box.',
			languages: ['go']
		},
		{
			name: 'GORM',
			icon: GORMLogo,
			text: 'GORM is one of the most used database ORMs for Go. I used it in my bachelors thesis as a wrapper around a postgres database and used it for easy, typesafe queries and automatic database migration.',
			languages: ['go']
		},
		{
			name: 'PostgreSQL',
			icon: PostgresLogo,
			text: 'Throughout various projects I used PostgreSQL as a database. I really like the compatibility and the huge ecosystem around it. I used it in my bachelors thesis to store data in a very performant way and found it to be a very good choice for a database. I also used it in a professional context at weiyu digital GmbH.',
			languages: []
		},
		{
			name: 'Google Cloud Platform',
			icon: GCPLogo,
			text: 'Some of my projects were hosted on the Google Cloud Platform. I used v-servers for smaller things and to learn about hosting, linux and deployment and used GCPs Cloud Run to deploy a automatic scaling version of a web api. I used GCPs build tools to auto deploy containers from a GitHub repo and the pub sub service to periodically run database cleanups. Although I find the GCPs web UI to be a bit clunky I enjoyed using and learning the Google Cloud Platform.',
			languages: []
		},
		{
			name: 'GitHub',
			icon: GitHubLogo,
			text: "Wether it's for hosting code, issues, pull requests or CI/CD pipelines, GitHub is the most popular platform for software development. I used it for most of my projects and utilized many of the features it provides, e.g. GitHub Actions to automatically build and deploy my projects to various platforms.",
			languages: []
		},
		{
			name: 'Node.js',
			icon: NodejsLogo,
			text: "Since Node.js is the most widespread runtime for JavaScript outside of the browser, I've used it quite a lot for all kinds of projects. Wether I needed a complex build script, a MQTT server or a live reloading project template, due to it's popularity and versatility Node.js could get the job done. In many projects Node.js is required for the build step of the project so in almost all of my web based projects I also use node. The native addon API allows interaction with node via a C++ interface which I used to write native Rust addons for Node.js.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Spring Boot',
			icon: undefined,
			text: 'Spring Boot is a framework for Java that makes it easy to create REST APIs. I mostly used it in a professional context while working as a full stack developer.',
			languages: ['java']
		},
		{
			name: 'Spigot',
			icon: SpigotLogo,
			text: 'I found my way into programming through Minecraft and the Craftbukkit/Spigot project by writing my own plugins for a Minecraft server. I spent countless hours in the game and learned the basics of programming by implementing administartive and minigame plugins to create a unique experience for the players of my server. It was a lot of fun and I still benefit of the things I learned back then.',
			languages: ['java']
		},
		{
			name: 'Selfhosting',
			icon: SelfhostedLogo,
			text: "Through r/selfhosted I got interested in deploying services I use on a day to day basis on my own hardware. Using a RaspberryPi as a small server at home I got into tools like Docker and Cloudflare tunnels to flexibly run and access services I need for myself or projects I work on. I got to experience a lot of advantages from this approch, mainly the low cost and high flexibility. I learned a lot in the process and I'm always looking for new things in the field.",
			languages: []
		},
		{
			name: 'Protractor',
			icon: ProtractorLogo,
			text: 'At my work as a full stack developer I have been tasked to e2e test an Angular app for a client. Before the switch to Cypress I used Protractor to write the tests. The original tests were written in plain JS. I converted the project into a TypeScript project and implemented a new, cleaner project structure. At the end of a full month of writing tests, all of the core workflows of the app were covered.',
			languages: ['typescript']
		},
		{
			name: 'gRPC',
			icon: gRPCLogo,
			text: 'I always found the concept of remote procedure calls for network communication very interesting. The idea of taking a familiar concept, the function call, and applying it to network communication is imo very developer friendly. Before implementing my own RPC framework to learn about the concept, I played around with gRPC and protobufs to learn about them and used them for a small hobby project.',
			languages: ['typescript', 'rust', 'go']
		},
		{
			name: 'Cloudflare',
			icon: undefined,
			text: "When it comes to hosting, protecting and administrating websites, Cloudflare is my go to service provider. I use it for it's simplicity and security features. For accessing my selfhosted services I use Clouflares tunnel service which allows easy access to my home server.",
			languages: []
		},
		{
			name: 'PWA',
			icon: PWALogo,
			text: "The continuous improvement of the web as an app platform has enabled the developers to bring amazing, native app like experiences to the web. With many interesting browser APIs a lot of things which previously required a native running app are now possible inside the browser. I've worked with quite a few of these APIs across multiple projects. E.g. in my bachelors thesis I implemented a fully offline working PWA which used the browsers indexed DB (through the dexie.js library) to manage work time data and enable optional syncing whenever a internet connection was given via a web worker.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Tailwind CSS',
			icon: TailwindLogo,
			text: "While learning Bootstrap I liked the concept of utility CSS classes complemented by custom CSS where necessary. When discovering Tailwind I immediately liked their approach of utility classes only. In combination with a component framework with style isolation this setup allows for a very flexible and maintainable styling approach. I've used it in many projects and I'm very satisfied with the flexibility and speed of development this approach gives me.",
			languages: []
		},
		{
			name: 'Directus',
			icon: DirectusLogo,
			text: "The flexibility and user experience of a headless CMS is a good fit for many projects. Directus is such a headless CMS and allows for easy setup without compromising on the users experience when it comes to managing data. I've used it in multiple projects as a selfhosted solution with a custom built frontend to fit the clients needs and I'm very satisfied with it. Especially the good support for internationalization of the apps is a big plus.",
			languages: ['javascript', 'typescript']
		},
		{
			name: 'Napi-RS',
			icon: NapirsLogo,
			text: 'Napi-RS is a library for writing Node.js addons in Rust. It utilizes the Node-API. I used it to create my own Rust based web server useable in Node.js. At first it was a little hard to get started since the project included a lot of async code and passing around JS handler functions but after overcoming these hurdles the advantages of running highly performant code in combination with easy to use Node.js became clear.',
			languages: ['rust', 'javascript', 'typescript']
		},
		{
			name: 'LSP',
			icon: LSPLogo,
			text: 'The Language Server Protocol allows a language server who analyzes source code and an IDE to communicate with each other. It allows to show errors and warnings in the IDE and to provide code completion and other features. I used it at a shallow level to provide assistance in a side project of mine.',
			languages: ['rust', 'typescript']
		},
		{
			name: 'MQTT',
			icon: MQTTLogo,
			text: 'In two projects I used MQTT to communicate IoT and sensor data to central server to write it into a timeseries database.',
			languages: []
		},
		{
			name: 'Electron',
			icon: ElectronLogo,
			text: 'In a project where a GUI around a CLI was needed I used Electron to create a cross platform desktop app. I really liked the combination of web and Node.js to to implement native features, it allowed to get productive really quickly.',
			languages: ["javascript", "typescript"]
		}
	].sort((a, b) => a.name.localeCompare(b.name));

	let checked = false;
</script>

<div class="flex w-100 justify-between mb-8">
	<div>
		<h1 id="skills" class="font-bold text-4xl">Skills</h1>
		<p>On the right side of each entry you can see associated tools that I also worked with.</p>
	</div>
	<div class="flex flex-col sm:flex-row items-center">
		<p class="font-semibold text-2xl mr-3 pb-1" class:underline={!checked}>Languages</p>
		<Switch bind:checked />
		<p class="font-semibold text-2xl ml-3 pb-1" class:underline={checked}>Tools</p>
	</div>
</div>

{#if !checked}
	{#each languages as lang}
		<Skill
			item={lang}
			refs={tools.filter((framework) =>
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
	{#each tools as framework}
		<Skill
			item={framework}
			refs={languages.filter((lang) =>
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
