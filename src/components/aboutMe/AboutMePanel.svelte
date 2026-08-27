<script>
    import {isHydrated, aboutMeOpen, theme, sidePanelOpen} from '../../constants.svelte.ts';
    import Pfp from "./Pfp.svelte";
    import Links from "./Links.svelte";
    import AboutMeText from "./AboutMeText.svelte";
    import TechStack from "./TechStack.svelte";
</script>

<div
        class="sidepanel"
        style:--hover-border={theme.fg_focused}
        style:--border-color={theme.fg}
        style:--hover-bg={theme.alt_bg_focused}
        style:--bg-color={theme.alt_bg}
        style:content-visibility={aboutMeOpen.value ? 'visible' : 'hidden'}
        style:width={aboutMeOpen.value ? '44vh' : 0}
        style:min-width={aboutMeOpen.value ? '44vh' : 0}
        style:border-width={aboutMeOpen.value ? '0.3vh' : 0}
        style:margin={aboutMeOpen.value ? '0 0 0 1vh' : '0'}
        style:transition={(isHydrated.value === false) ? '' : `background-color 0.25s ease, border-color 0.25s ease, width 0.25s ease, min-width 0.25s ease, margin 0.25s ease, border-width 0s ease ${aboutMeOpen.value ? 0 : 0.25}s`}
>
    <div class="linkspfp">
        <Links/>
        <Pfp/>
    </div>

    <AboutMeText/>
    <TechStack/>

    <p class="pawnote">⨺⃝ &nbsp;We stay awesome &lt;3</p>
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
        align-items: center;
        gap: 2vh;
        overflow: hidden;
        max-width: 44vh;
    }

    .sidepanel:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }

    .linkspfp {
        display: flex;
        flex-direction: row;
        padding-left: 2vh;
        padding-top: 3vh;
        text-align: right;
        align-items: center;
    }

    .pawnote {
        margin-top: auto;
        font-style: italic;
        font-size: 1.1vh;
        color: var(--border-color);
        opacity: 0.6;
        text-align: center;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
    }
</style>
