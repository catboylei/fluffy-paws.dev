<script>
	import { sidePanelOpen } from '../../constants.svelte.ts';
	import { theme } from '../../constants.svelte.ts';

	function handleClicked() {
		sidePanelOpen.value = !sidePanelOpen.value;
	}
</script>

<!-- i know i should just use an svg but better control on animations,,,,, -->

<button class="menubutton" aria-label="menu" onclick={handleClicked}>
	<span class="bunger top" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}
	></span>
	<span class="bunger middle" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}
	></span>
	<span class="bunger bottom" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}
	></span>
</button>

<style>
	.menubutton {
		height: 3vh;
		width: 3vh;
		background-color: transparent;
		border-width: 0;
		margin-right: 2vh;
		margin-left: 0.8vh;
	}

	.bunger {
		display: block;
		height: 0.2vh;
		border-width: 0;
		background-image: linear-gradient(var(--bg-color), var(--bg-color));
		background-repeat: no-repeat;
		transition: margin-left 0.25s ease;
	}

	.top {
		width: 2vh;
		margin-left: 0;
	}

	.middle {
		width: 3vh;
		margin-top: 0.8vh;
		margin-bottom: 0.8vh;
	}

	.bottom {
		width: 2vh;
		margin-left: 1vh;
	}

	.menubutton:hover .bunger {
		background-image: linear-gradient(var(--hover-color), var(--hover-color));
	}

	.menubutton:hover .bottom {
		margin-left: 0;
	}

	.menubutton:hover .top {
		margin-left: 1vh;
	}
</style>
