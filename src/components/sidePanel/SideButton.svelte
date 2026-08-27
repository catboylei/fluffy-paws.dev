<script>
	import { theme } from '../../constants.svelte.ts';
	import { slide } from 'svelte/transition';
	const { button, children } = $props();
	let isOpen = $derived(button.title === 'My Projects');

	function handleClicked() {
		isOpen = !isOpen;
	}
</script>

<div class="side-button">
	<button style:--color={theme.fg} style:--hover-color={theme.fg_focused} onclick={handleClicked}>
		{button.title}
		<span class="icon" style:transform={isOpen ? 'rotate(90deg)' : ''}></span>
	</button>
	{#if isOpen}
		<div class="children" style:--side-color={theme.greyed_out} transition:slide>
			{@render children?.()}
		</div>
	{/if}
</div>

<style>
	button {
		border-width: 0;
		display: flex;

		width: fit-content;
		white-space: nowrap;

		margin-bottom: 0.4vh;

		font-size: 2.2vh;
		font-weight: 700;
		font-family: SpaceGrotesk, monospace;

		color: var(--color);

		background-color: transparent;

		transition: color 0.25s ease;
	}

	button:hover {
		color: var(--hover-color);
	}

	.icon {
		margin-top: 0.3vh;
		margin-left: 0.5vh;
		display: block;
		height: 2.2vh;
		width: 2.2vh;
		mask: url('/icons/theshape.svg') no-repeat center / contain;
		-webkit-mask: url('/icons/theshape.svg') no-repeat center / contain;
		background-color: CurrentColor;
		transition:
			background-color 0.25s ease,
			transform 0.25s ease;
	}

	.side-button {
		display: flex;
		flex-direction: column;
		width: fit-content;

		margin-right: 1vh;
		margin-left: 2.4vh;
		margin-bottom: 1vh;
	}

	.children {
		display: flex;
		flex-direction: column;
		align-items: start;
		border-left: 0.3vh solid var(--side-color);
		margin-left: 1vh;
	}
</style>
