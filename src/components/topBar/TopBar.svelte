<script>
	import { theme } from '../../constants.svelte.ts';
	import TopButton from './TopButton.svelte';
	import MenuButtonFancy from './MenuButtonFancy.svelte';
	import Separator from './Separator.svelte';
	import Thetadelta from './Thetadelta.svelte';
</script>

<div
	class="topbar"
	style:--hover-border={theme.fg_focused}
	style:--border-color={theme.fg}
	style:--hover-bg={theme.alt_bg_focused}
	style:--bg-color={theme.alt_bg}
>
	<div class="topbar-side">
		<MenuButtonFancy />
		<Separator />
		<TopButton button={{ title: 'Home', link: '/' }} />
		<Separator />
		<TopButton button={{ title: 'My Projects', link: '/projects' }} />
	</div>
	<div class="topbar-middle" style:justify-content="center">
		<Thetadelta color="femboy" />
	</div>
	<div class="topbar-side" style:justify-content="right">
		<TopButton button={{ title: 'About Me', link: '/about' }} />
	</div>
</div>

<style>
	.topbar {
		display: flex;

		height: 50px;

		border-radius: 10px;
		border-width: 2px;
		border-style: solid;
		border-color: var(--border-color);

		background-color: var(--bg-color);

		margin: 12px;
		padding-left: 2px;
		padding-right: 8px;

		transition:
			background-color 0.25s ease,
			border-color 0.25s ease;
	}

	.topbar:hover {
		background-color: var(--hover-bg);
		border-color: var(--hover-border);
	}

	.topbar-side {
		display: flex;
		align-items: center;

		width: 40%;
		height: 50px;
	}

	.topbar-middle {
		display: flex;
		align-items: center;

		width: 20%;
		height: 50px;
	}
</style>
