<script>
    import {theme} from "../constants.svelte.ts";
    import Meow from "./Meow.svelte";
</script>

<div
        class="topbar"
        style:background-color={theme.alt_bg}
        style:border-color={theme.fg}
>
    <div class="topbar-half">
        <Meow/>
        <Meow/>
    </div>
    <div class="topbar-half" style:justify-content="right">
        <Meow/>
        <Meow/>
    </div>
</div>

<style>
    .topbar {
        display: flex;

        height: 60px;

        border-radius: 10px;
        border-width: 2px;
        border-style: solid;

        margin: 12px;
    }

    .topbar-half {
        display: flex;
        align-items: center;

        width: 50%;
        height: 60px;
    }
</style>