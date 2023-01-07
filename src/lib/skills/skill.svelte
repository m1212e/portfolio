<script lang="ts">
	import Chevron from '../../icons/dark-chevron-down.svg';
	import { createEventDispatcher } from 'svelte';
	import { onMount } from 'svelte';

	const dispatch = createEventDispatcher();

	export let item: {
		name: string;
		icon: string;
		text: string;
	};

	export let refs: {
		name: string;
		icon: string;
	}[];

	let expanded = false;
	let contentElement: HTMLDivElement;
	let needsExpandButton = true;

	onMount(() => {
		if (contentElement.clientHeight < contentElement.scrollHeight) {
			needsExpandButton = true;
		} else {
			needsExpandButton = false;
		}
	});
</script>

<button
	id={item.name}
	class="border-2 border-black rounded-xl p-4 flex flex-col items-center my-3 w-full lg:w-4/5 {needsExpandButton ? 'pb-0' : ''}}"
	on:click={() => (expanded = !expanded)}
>
	<div class="flex w-full">
		<img src={item.icon} alt="{item.name} logo" class="h-20 w-20" />
		<div class="content divide-x divide-black flex" class:expanded bind:this={contentElement}>
			<div class="flex items-start ml-3 flex-col w-4/5">
				<h3 class="font-bold text-2xl">
					{item.name}
				</h3>
				<p class="text-left mr-4">
					{item.text}
				</p>
			</div>
			{#if refs.length > 0}
				<div class="pl-4">
					{#each refs as ref}
						<div class="flex items-center hover:underline">
							<button class="flex" on:click={() => dispatch('refClicked', ref)}>
								{#if ref.icon}
									<img class="h-6 w-6 mr-2 pt-1" src={ref.icon} alt="{ref.name} logo" />
								{/if}
								{ref.name}
							</button>
						</div>
					{/each}
				</div>
			{/if}
		</div>
	</div>
	{#if needsExpandButton}
		<img class="chevron" src={Chevron} alt="chevron to indicate expansion state" class:expanded />
	{/if}
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
