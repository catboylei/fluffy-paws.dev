<script>
	import {isHydrated, sidePanelOpen, theme} from '../../constants.svelte.ts';
	import SideButton from './SideButton.svelte';
	import SideGoober from './SideGoober.svelte';

	// todo since this panel is fairly small, split it in 2 with dynamic height and have something else under it
</script>

<div
	class="sidepanel"
	style:--hover-border={theme.fg_focused}
	style:--border-color={theme.fg}
	style:--hover-bg={theme.alt_bg_focused}
	style:--bg-color={theme.alt_bg}
	style:content-visibility={sidePanelOpen.value ? 'visible' : 'hidden'}
	style:width={sidePanelOpen.value ? '24vh' : 0}
	style:min-width={sidePanelOpen.value ? '24vh' : 0}
	style:border-width={sidePanelOpen.value ? '0.3vh' : 0}
	style:margin={sidePanelOpen.value ? '0 1vh 0 0' : '0'}
	style:transition={(isHydrated.value === false) ? '' : `background-color 0.25s ease, border-color 0.25s ease, width 0.25s ease, min-width 0.25s ease, margin 0.25s ease, border-width 0s ease ${sidePanelOpen.value ? 0 : 0.25}s`}
>
	<SideButton button={{ title: 'My Projects' }}>
		<SideGoober button={{ title: 'BfDisplay-rs', link: '/projects#BfDisplay-rs' }} />
		<SideGoober button={{ title: 'Meow Macro', link: '/projects#Meow Macro' }} />
		<SideGoober button={{ title: 'Nixanthropy', link: '/projects#Nixanthropy' }} />
		<SideGoober button={{ title: 'Greg Utils', link: '/projects#Greg Utils' }} />
		<SideGoober button={{ title: 'Live Majin Reaction', link: '/projects#Live Majin Reaction' }} />
		<SideGoober button={{ title: 'fluffypaws.dev', link: '/projects#fluffypaws.dev' }} />
		<SideGoober button={{ title: 'SimpleWifi-rs', link: '/projects#SimpleWifi-rs' }} />
		<SideGoober button={{ title: 'CatboyAddons-ct', link: '/projects#CatboyAddons-ct' }} />
	</SideButton>
	<SideButton button={{ title: 'Something Else' }} />
	<SideButton button={{ title: 'Private' }}>
		<SideGoober button={{ title: ' Guild Doc', link: '/projects/guilddoc' }} />
		<SideGoober button={{ title: ' High Rank Doc', link: '/projects/hrdoc' }} />
	</SideButton>
</div>

<style>
	.sidepanel {
		padding-top: 2.4vh;
		display: flex;
		flex-direction: column;
		border-radius: 1vh;
		border-style: solid;
		border-color: var(--border-color);
		background-color: var(--bg-color);
		overflow: hidden;
		max-width: 24vh;
	}

	.sidepanel:hover {
		background-color: var(--hover-bg);
		border-color: var(--hover-border);
	}
</style>
