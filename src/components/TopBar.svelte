<script>

    // todo save hovered state when redirecting and also animation on first render ?

    import {theme} from "../constants.svelte.ts";
    import TopButton from "./TopButton.svelte";
</script>

<div
        class="topbar"
        style:border-color={theme.fg}
        style:--bg={theme.alt_bg}
        style:--hover-bg={theme.alt_bg_focused}
>
    <div class="topbar-half">
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

        background-color: var(--bg);

        margin: 12px;
        padding-left: 8px;
        padding-right: 8px;

        transition: background-color 0.5s ease;
    }

    .topbar:hover {
        background-color: var(--hover-bg);
    }

    .topbar-half {
        display: flex;
        align-items: center;

        width: 50%;
        height: 50px;
    }
</style>