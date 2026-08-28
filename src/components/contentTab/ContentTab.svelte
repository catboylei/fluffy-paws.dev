<script>
	import { theme } from '../../constants.svelte.ts';
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
		flex-direction: column;

		width: 100%;

		border-radius: 1vh;
		border-width: 0.3vh;
		border-style: solid;
		border-color: var(--border-color);

		background-color: var(--bg-color);

		transition: background-color 0.25s ease, border-color 0.25s ease;
		align-items: center;

		flex: 1;
		min-height: 0;
		overflow-y: auto;
		overflow-x: hidden;
		box-sizing: border-box;

		scrollbar-width: thin;
		scrollbar-color: var(--border-color) var(--bg-color);
	}

	.contenttab:hover {
		background-color: var(--hover-bg);
		border-color: var(--hover-border);
	}
</style>
