<script lang="ts">
	import Chevron from '../../icons/dark-chevron-down.svg';

	export let lang: {
		name: string;
		icon: string;
		text: string;
	};

	export let frameworks: {
		name: string;
		icon: string;
		languages: string[];
	}[];

	let expanded = false;
</script>

<button
	class="border-2 border-black rounded-xl p-4 pb-0 flex flex-col items-center"
	on:click={() => (expanded = !expanded)}
>
	<div class="flex">
		<img src={lang.icon} alt="language logo" class="h-20 w-20" />
		<div class="content divide-x divide-black flex" class:expanded>
			<div class="flex items-start ml-3 flex-col">
				<h3 class="font-bold text-2xl">
					{lang.name}
				</h3>
				<p class="w-96 text-left">
					{lang.text}
				</p>
			</div>
			<div class="pl-4">
				{#each frameworks.filter( (f) => f.languages.find((l) => l.toLowerCase() == lang.name.toLowerCase()) ) as framework}
					<div class="flex items-center">
						{#if framework.icon}
							<img
								class="h-6 w-6 mr-2 pt-1"
								src={framework.icon}
								alt="{framework.name} logo"
							/>
						{/if}
						{framework.name}
					</div>
				{/each}
			</div>
		</div>
	</div>
	<img class="chevron" src={Chevron} alt="chevron to indicate expansion state" class:expanded />
</button>

<style>
	.content {
		max-height: 5rem;
		transition: max-height 0.3s cubic-bezier(0, 1, 0, 1);
		overflow: hidden;
	}

	.content.expanded {
		max-height: 100rem;
		transition: max-height 1s ease-in-out;
	}

	.chevron {
		@apply w-8 h-8 scale-125 duration-300;
	}

	.chevron.expanded {
		@apply rotate-180;
	}
</style>
