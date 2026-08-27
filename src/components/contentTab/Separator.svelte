<script>
import {theme} from "../../constants.svelte.ts";

const { text } = $props();
</script>

<div id={text}
        class="separator"
        style:--color={theme.greyed_out}
        style:--text-color={theme.fg}
        style:hover-color={theme.fg_focused}
>
    <span class="side"></span>
    <div class="text"> {text} </div>
    <span class="side"></span>
</div>

<style>
    .separator {
        width: 90%;
        gap: 1vh;
        display: flex;
        flex-direction: row;
        align-items: center;
        margin-top: 2vh;
    }

    .side {
        flex: 1;
        display: block;
        height: 0.3vh;
        background-color: var(--color);
    }

    .text {
        color: var(--text-color);
        transition: color 0.25s ease;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        font-weight: 700;
        font-size: 1.5vh;
    }

    .separator:hover .text {
        color: var(--hover-color);
    }
</style>