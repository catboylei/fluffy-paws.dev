<script>
	import { theme } from '../../constants.svelte.ts';
	const { button } = $props();

	function openPage() {
		window.location.href = button.link;
	}
</script>

<button
	class="button"
	onclick={openPage}
	style:--color={theme.fg}
	style:--hover-color={theme.fg_focused}
>
	{button.title}
</button>

<style>
	.button {
		border-width: 0;
		white-space: nowrap;

		font-size: 13px;
		font-weight: 700;
		font-family: SpaceGrotesk, NerdFonts, monospace;

		color: var(--color);

		background-color: transparent;

		margin-right: 12px;
		margin-left: 12px;
	}

	.button:hover {
		color: var(--hover-color);
	}
</style>
