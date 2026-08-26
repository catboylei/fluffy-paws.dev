<script>
	import { theme } from '../constants.svelte.ts';
</script>

<div
	class="contenttab"
	style:--hover-border={theme.fg_focused}
	style:--border-color={theme.fg}
	style:--hover-bg={theme.alt_bg_focused}
	style:--bg-color={theme.alt_bg}
>
	<slot />
</div>

<style>
	.contenttab {
		display: flex;
		flex-direction: row;

		width: 100%;

		border-radius: 1vh;
		border-width: 0.3vh;
		border-style: solid;
		border-color: var(--border-color);

		background-color: var(--bg-color);

		margin: 0 1vh 0 0;

		padding-left: 0.2vh;
		padding-right: 0.8vh;

		transition:
			background-color 0.25s ease,
			border-color 0.25s ease;
	}

	.contenttab:hover {
		background-color: var(--hover-bg);
		border-color: var(--hover-border);
	}
</style>
