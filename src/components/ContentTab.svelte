<script>
    import {theme} from "../constants.svelte.ts";
</script>

<div class="contenttab"
     style:--hover-border={theme.fg_focused}
     style:--border-color={theme.fg}
     style:--hover-bg={theme.alt_bg_focused}
     style:--bg-color={theme.alt_bg}
>
    <slot/>
</div>

<style>
    .contenttab {
        display: flex;
        flex-direction: row;

        width: 100%;

        border-radius: 10px;
        border-width: 2px;
        border-style: solid;
        border-color: var(--border-color);

        background-color: var(--bg-color);

        margin: 0 12px 0 0;

        padding-left: 2px;
        padding-right: 8px;

        transition: background-color 0.25s ease, border-color 0.25s ease;
    }

    .contenttab:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }
</style>