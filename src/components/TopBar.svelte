<script>
    import {theme} from "../constants.svelte.ts";
    import TopButton from "./TopButton.svelte";
    import MenuButtonFancy from "./MenuButtonFancy.svelte";
</script>

<div
        class="topbar"
        style:--hover-border={theme.fg_focused}
        style:--border-color={theme.fg}
        style:--hover-bg={theme.alt_bg_focused}
        style:--bg-color={theme.alt_bg}
>
    <div class="topbar-half">
        <MenuButtonFancy/>
        <TopButton button={{ title: "Home", link: "/"}}/>
    </div>
    <div class="topbar-half" style:justify-content="right">
        <TopButton button={{ title: "About", link: "/about"}}/>
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

        transition: background-color 0.25s ease, border-color 0.25s ease;
    }

    .topbar:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }

    .topbar-half {
        display: flex;
        align-items: center;

        width: 50%;
        height: 50px;
    }
</style>