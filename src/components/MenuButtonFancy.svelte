<script>
    import {theme} from "../constants.svelte.ts";
</script>

<!-- i know i should just use an svg but better control on animations,,,,, -->

<button class="menubutton" aria-label="menu">
    <span class="bunger top" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}></span>
    <span class="bunger middle" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}></span>
    <span class="bunger bottom" style:--bg-color={theme.fg} style:--hover-color={theme.fg_focused}></span>
</button>

<style>
    .menubutton {
        height: 30px;
        width: 30px;
        background-color: transparent;
        border-width: 0;
        margin-right: 20px;
        margin-left: 8px;
    }

    .bunger {
        display: block;
        height: 2px;
        border-width: 0;
        background-image: linear-gradient(var(--bg-color), var(--bg-color));
        background-repeat: no-repeat;
        transition: margin-left 0.25s ease;
    }

    .top {
        width: 20px;
        margin-left: 0;
    }

    .middle {
        width: 30px;
        margin-top: 8px;
        margin-bottom: 8px;
    }

    .bottom {
        width: 20px;
        margin-left: 10px;
    }

    .menubutton:hover .bunger {
        background-image: linear-gradient(var(--hover-color), var(--hover-color));
    }

    .menubutton:hover .bottom {
        margin-left: 0
    }

    .menubutton:hover .top {
        margin-left: 10px
    }
</style>
