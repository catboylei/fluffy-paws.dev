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
        style:width={aboutMeOpen.value ? '440px' : 0}
        style:min-width={aboutMeOpen.value ? '440px' : 0}
        style:border-width={aboutMeOpen.value ? '2px' : 0}
        style:margin={aboutMeOpen.value ? '0 12px 0 0' : '0'}
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
        padding-top: 24px;
        display: flex;
        flex-direction: column;
        border-radius: 10px;
        border-style: solid;
        border-color: var(--border-color);
        background-color: var(--bg-color);
        align-items: center;
        gap: 24px;
        overflow: hidden;
        max-width: 440px;
    }

    .sidepanel:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }

    .linkspfp {
        display: flex;
        flex-direction: row;
        padding-left: 24px;
        text-align: right;
        align-items: center;
    }

    .pawnote {
        margin-top: auto;
        font-style: italic;
        font-size: 12px;
        color: var(--border-color);
        opacity: 0.6;
        text-align: center;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
    }
</style>
