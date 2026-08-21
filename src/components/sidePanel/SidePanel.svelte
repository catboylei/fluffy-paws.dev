<script>
    import {theme} from "../../constants.svelte.ts";
    import {nav} from "../../constants.svelte.ts";
    import SideButton from "./SideButton.svelte";
    import TopButton from "../topBar/TopButton.svelte";
    import SideGoober from "./SideGoober.svelte";
</script>

<div class="sidepanel"
     style:--hover-border={theme.fg_focused}
     style:--border-color={theme.fg}
     style:--hover-bg={theme.alt_bg_focused}
     style:--bg-color={theme.alt_bg}
     style:content-visibility={(nav.isOpen) ? "visible" : "hidden"}
     style:width={(nav.isOpen) ? "220px" : 0}
     style:border-width={(nav.isOpen) ? "2px" : 0}
     style:margin={nav.isOpen ? '0 12px 0 0' : '0'}
     style:transition={`background-color 0.25s ease, border-color 0.25s ease, width 0.25s ease, margin 0.25s ease, border-width 0s ease ${(nav.isOpen) ? 0 : 0.25}s`}
>
    <SideButton button={{ title: "My Projects"}}>
        <SideGoober button={{ title: "BfDisplay-rs", link: "/projects/bfdisplay-rs"}}/>
        <SideGoober button={{ title: "Nixanthropy", link: "/projects/nixanthropy"}}/>
        <SideGoober button={{ title: "Meow-Macro", link: "/projects/meow-macro"}}/>
        <SideGoober button={{ title: "fluffy-paws.dev", link: "/projects/fluffypaws"}}/>
        <SideGoober button={{ title: "GregUtils", link: "/projects/gregutils"}}/>
        <SideGoober button={{ title: "CatboyAddons", link: "/projects/catboyaddons"}}/>
    </SideButton>
    <SideButton button={{ title: "Something Else"}}/>
    <SideButton button={{ title: "Private"}}>
        <SideGoober button={{ title: " Guild Doc", link: "/projects/guilddoc"}}/>
        <SideGoober button={{ title: " High Rank Doc", link: "/projects/hrdoc"}}/>
    </SideButton>
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
    }

    .sidepanel:hover {
        background-color: var(--hover-bg);
        border-color: var(--hover-border);
    }
</style>