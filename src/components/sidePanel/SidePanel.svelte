<script>
    import {theme} from "../../constants.svelte.ts";
    import {nav} from "../../constants.svelte.ts";
</script>

<div class="sidepanel"
     style:--hover-border={theme.fg_focused}
     style:--border-color={theme.fg}
     style:--hover-bg={theme.alt_bg_focused}
     style:--bg-color={theme.alt_bg}
     style:width={(nav.isOpen) ? "250px" : 0}
     style:border-width={(nav.isOpen) ? "2px" : 0}
     style:margin={nav.isOpen ? '0 12px 0 0' : '0'}
     style:transition={`background-color 0.25s ease, border-color 0.25s ease, width 0.25s ease, margin 0.25s ease, border-width 0s ease ${(nav.isOpen) ? 0 : 0.25}s`}
>

</div>

<style>
    .sidepanel {
        display: flex;
        flex-direction: row;
        border-radius: 10px;
        border-style: solid;
        border-color: var(--border-color);
        background-color: var(--bg-color);
    }

    .sidepanel:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }
</style>