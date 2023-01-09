<script>
	import Me from '../images/me.jpeg';
	import Github from '../icons/white-github.svg';
	import Mail from '../icons/white-mail.svg';
</script>

<div class="flex items-center flex-col-reverse md:flex-row max-w-4xl">
	<div>
		<h1 id="home" class="font-bold text-6xl">Hi!</h1>
		<p class="text-3xl md:w-3/4 mt-8 mb-7">
			I’m Felix, a Software Engineer from Hamburg, Germany.
			<br />
			Specialized in Web-Development,
			<br />
			inquisitive to everything else.
		</p>
		<div class="flex">
			<a href="https://github.com/m1212e">
				<button class="bg-gray-800 text-white font-bold text-lg rounded-full flex py-2 px-4">
					GitHub <img class="pl-3" src={Github} alt="github logo" />
				</button>
			</a>
			<a href="mailto:m1212e@proton.me">
				<button class="bg-blue-600 text-white font-bold text-lg rounded-full flex py-2 px-4 ml-3">
					Contact <img class="pl-3" src={Mail} alt="mail icon" />
				</button>
			</a>
		</div>
	</div>
	<img src={Me} alt="portrait of me" class="rounded-full h-72 w-72 mb-16" />
</div>
