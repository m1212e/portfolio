<script lang="ts">
	import Menu from '../icons/menu.svg';
	import GitHub from '../icons/dark-github.svg';
	import Logo from '../images/logo.svg';

	let expanded = false;

	function close() {
		expanded = false;
	}
</script>

<nav class="flex flex-col">
	<div class="closer" class:expanded on:click={close} on:keypress={close} />
	<div class="white-bg" class:expanded />
	<button class="menu-button" on:click={() => (expanded = true)} class:expanded>
		<img src={Menu} alt="menu icon" />
	</button>

	<img class="logo" src={Logo} alt="logo" class:expanded />
	<div class="links" class:expanded>
		<a on:click={close} href="#home">Home</a>
		<a on:click={close} href="#career">Career</a>
		<a on:click={close} href="#skills">Skills</a>
		<a on:click={close} href="#showcase">Showcase</a>
		<a class="mt-3" href="https://github.com/m1212e"><img class="h-7" src={GitHub} alt="github logo"></a>
	</div>
</nav>

<style>
	.menu-button {
		z-index: 3;
		position: fixed;
		right: 0.5rem;
		top: 3.7rem;
		transition: all 0.2s ease-in-out;
	}

	.menu-button.expanded {
		right: -2rem;
	}

	.white-bg {
		z-index: 2;
		background-color: white;
		height: 3rem;
		width: 2.8rem;
		position: fixed;
		right: 0;
		top: 3rem;
		border-radius: 1rem 0 0 1rem;
		border-color: black;
		border-width: 0.2rem 0 0.2rem 0.2rem;
		transition: all 0.2s ease-in-out;
	}

	.white-bg.expanded {
		right: -2rem;
		top: -2rem;
		height: 25rem;
		width: 18rem;
		border-radius: 3rem 0 3rem 8rem;
	}

	.closer {
		position: fixed;
		left: 0;
		top: 0;
		z-index: 1;
		width: 100vw;
		height: 100vh;
		display: none;
	}

	.closer.expanded {
		display: block;
	}

	.links {
		z-index: 3;
		position: fixed;
		right: -10rem;
		top: 9rem;
		display: flex;
		flex-direction: column;
		transition: all 0.2s ease-in-out;
		@apply font-bold text-3xl;
	}

	.links.expanded {
		right: 4rem;
	}

	.logo {
		z-index: 3;
		position: fixed;
		right: -15rem;
		top: 1rem;
		height: 8rem;
		transition: all 0.2s ease-in-out;
	}

	.logo.expanded {
		right: 0rem;
	}

	@media (min-width: 640px) {
		.menu-button {
			display: none;
		}
		.white-bg {
			display: none;
		}
		.closer {
			display: none;
		}

		.logo {
			top: 0;
			right: 0;
		}
		.links {
			right: 4rem;
			top: 8rem;
		}
	}
</style>
