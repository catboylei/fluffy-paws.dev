<script>
import {theme} from "../constants.svelte.ts";
</script>

<button class="menubutton" style:--color-focused={theme.fg_focused} style:--color={theme.fg}>
    <span class="thetadelta"></span>
</button>

<style>
    .thetadelta {
        display: inline-block;
        width: 40px;
        height: 40px;
        mask: url('/icons/bunger.svg') no-repeat center / contain;
        -webkit-mask: url('/icons/bunger.svg') no-repeat center / contain;
        background-color: CurrentColor;
    }

    .menubutton {
        background-color: transparent;
        border-width: 0;
        margin-top: 4px;
        color: var(--color);
        transition: color 0.25s ease;
    }

    .menubutton:hover {
        color: var(--color-focused);
    }
</style>