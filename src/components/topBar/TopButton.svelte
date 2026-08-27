<script>
	import {aboutMeOpen, theme} from '../../constants.svelte.ts';
	const { button } = $props();

	function handleClicked() {
		if (button.link) window.location.href = button.link;
		if (button.about) aboutMeOpen.value = !aboutMeOpen.value;
	}
</script>

<button
	class="button"
	onclick={handleClicked}
	style:--color={theme.fg}
	style:--hover-color={theme.fg_focused}
>
	{button.title}
</button>

<style>
	.button {
		border-width: 0;

		height: 4vh;

		font-size: 1.8vh;
		font-weight: 700;
		font-family: SpaceGrotesk, monospace;

		color: var(--color);

		background-color: transparent;
		background-repeat: no-repeat;
		background-position: center bottom;
		background-image: linear-gradient(currentColor, currentColor);
		transition: background-size 0.25s ease;
		background-size: 0 0.3vh;
		background-position-y: 3vh;

		margin-right: 1vh;
		margin-left: 1vh;
	}

	.button:hover {
		background-size: 80% 0.3vh;
		color: var(--hover-color);
	}
</style>
