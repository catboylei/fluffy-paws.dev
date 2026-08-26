<script>
    import {isHydrated, aboutMeOpen, theme} from '../../constants.svelte.ts';
    import Pfp from "./Pfp.svelte";
</script>

<div
        class="sidepanel"
        style:--hover-border={theme.fg_focused}
        style:--border-color={theme.fg}
        style:--hover-bg={theme.alt_bg_focused}
        style:--bg-color={theme.alt_bg}
        style:content-visibility={aboutMeOpen.value ? 'visible' : 'hidden'}
        style:width={aboutMeOpen.value ? '660px' : 0}
        style:border-width={aboutMeOpen.value ? '2px' : 0}
        style:margin={aboutMeOpen.value ? '0 12px 0 0' : '0'}
        style:transition={(isHydrated.value === false) ? '' : `background-color 0.25s ease, border-color 0.25s ease, width 0.25s ease, margin 0.25s ease, border-width 0s ease ${aboutMeOpen.value ? 0 : 0.25}s`}
>
    <div class="linkspfp">
        <div>meow meow meow meow meow meow meow</div>
        <Pfp/>
    </div>
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
        align-items: end;
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
    }
</style>
