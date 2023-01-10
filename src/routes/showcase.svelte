<script lang="ts">
	import TimetrackerScreenshot from '../images/timetracker-screenshot.png';
	import IdeaAppScreenshot1 from '../images/ideaapp-1.jpg';
	import IdeaAppScreenshot2 from '../images/ideaapp-2.jpg';
	import IdeaAppScreenshot3 from '../images/ideaapp-3.jpg';
	import DGDLScreenshot from '../images/das-gesicht-der-liebe-screenshot.png';
</script>

<h1 id="showcase" class="font-bold text-4xl mb-6">Timetracker</h1>
<div style="height: 30rem;" class="shadow-lg overflow-scroll mb-10">
	<img src={TimetrackerScreenshot} alt="screenshot of my timetracker app" />
</div>
<p>
	The above image shows the landing page of my app "Timetracker". I built it as a case study for my
	Bachelors thesis to examine a web apps performance using various technologies. The app was
	implemented with SvelteKit as a progressive web app, installable and fully functional when
	offline. It featured user accounts, syncing across devices, sharing data between user accounts,
	exporting into various formats like excel templates and of course: Tracking worktime. After
	finalization the app was quite polished, the Go backend capable of managing tens of thousands of
	users at the same time running on a single core server with ~500mb RAM. It was a fun experience
	and during my time working as an employee actually very useful since it provided exactly the tools
	and features I needed to track my worktime.
</p>

<h1 class="font-bold text-4xl mt-14 mb-6">I got an idea</h1>
<div style="height: 45rem;" class="shadow-lg overflow-scroll my-10 md:px-32 lg:px-52 xl:px-96">
	<img src={IdeaAppScreenshot1} alt="screenshot of my idea app" />
	<img class="my-2" src={IdeaAppScreenshot2} alt="screenshot of my idea app" />
	<img src={IdeaAppScreenshot3} alt="screenshot of my idea app" />
</div>
<p>
	"I got an idea" was a React Native mobile app developed as a project for university. Using Firebase
	as a backend it allowed for creation and categorization of ideas, bringing together people who
	have ideas for IT projects and those who have the skills to implement them. It featured user
	accounts, filtering by categories, account customization and a realtime chat where people could
	exchange their opinion over a project. The app was able to locally cache projects to minimize the
	amount of transferred data, while browsing the lazy loading infinite scroll project list. I worked
	on the app in cooperation with a friend of mine.
</p>

<h1 class="font-bold text-4xl mt-14 mb-6">Das Gesicht der Liebe</h1>
<div style="height: 30rem;" class="shadow-lg overflow-scroll mb-10 flex justify-center lg:px-60">
	<img style="width: 100%; height: fit-content;" src={DGDLScreenshot} alt="screenshot of das-gesicht-der-liebe.de" />
</div>
<p>
	"Das Gesicht der Liebe" - The face of Love is a <a
		class="underline"
		href="https://das-gesicht-der-liebe.de">website</a
	> I designed and implemented for a friend of mine. She started a charity organization to help people
	in Antigua, Guatemala and asked me if I could help her creating a website to show her work. So we started
	brainstorming and discussing her requirements, and I put together a prototype using Figma. After a
	few design iterations I started planning the tech stack. Since it was necessary to keep the costs as
	low as possible, I decided to selfhost the headless CMS (Directus) as a Docker container on my RaspberryPi
	and grant her access via Cloudflare Tunnels. Then I created a frontend app and used SvelteKits prerendering
	functionality to generate static HTML files from the Directus contents. To trigger a rebuild and deploy
	whenever she makes changes, I set up Cloudflare hosting and configured a webhook. She was very happy
	with the results and I was happy to help her.
</p>

<h1 class="font-bold text-4xl mt-14 mb-6">easy-rpc</h1>
<p>
	<a class="underline" href="https://github.com/m1212e/easy-rpc">easy-rpc</a> is a rpc framework for
	the web. Initially started to learn about parsers and the Go programming language I continued working on it and by now it is an actually useable RPC framework based on HTTP.
    Throughout the process I switched to Rust, which was a good decision, I really started appreciating the language and its features. I learned so much with this project
    and had a lot of fun since I needed to solve problems I had never encountered before. I am still working on it and plan to add more features in the future.
    But not only the parser and transpiler are written in Rust, even the web server serving incoming rpc requests is built with Rust. Since the tool should support TypeScript, I
    created a wrapper to enable usage via the node-api which allows developers to write native addons for Node.js.
    The tool also provides a VSCode addon and a language server based on the Microsoft Language Server Protocol to support the developers while they are writing their code.
</p>
