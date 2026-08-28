<script>
import {theme} from "../../constants.svelte.ts";
import Separator from "./Separator.svelte";
import Project from "./Project.svelte";

// todo if vw < vh/2 make image size smaller to accomodate
</script>

<div class="top"
     style:--hover-color={theme.fg_focused}
     style:--color={theme.fg}>
    <div class="text">
        My Projects
    </div>
    <div class="desc text">
        Welcome to my projects ! <br>
        Here I will showcase all my currently public projects.
    </div>

    <Separator text="Mature / Finished Projects"/>

    <Project
            src="/showcases/bfDisplay-rs.png"
            align="end"
            title="BfDisplay-rs"
            desc='NeoVim plugin to live evaluate Brainfuck code, configurable Syntax Highlight,
            I/O, live detect infinite loops and more. <br><br>
            This plugin uses non-blocking Rust binary to optimize performance and avoid slow single-threaded lua logic. <br><br>'
            link="https://github.com/catboylei/bfDisplay-rs"
    />

    <Project
            src="/showcases/MeowMacro.png"
            align="start"
            title="Meow Macro"
            desc='CLI tool written in Rust, used to manage and write simple game macros with no prior coding experience <br><br>
            Kinda like a Linux-only, CLI, simpler version of AutoHotKey I suppose <br><br>'
            link="https://github.com/catboylei/meow-macro"
    />

    <Separator text="In Progress / Unfinished Projects"/>

    <Project
            src="/showcases/Nixanthropy.png"
            align="end"
            title="Nixanthropy"
            desc="My personal NixOs config, perpetually a WIP but always in a usable state ! <br><br>
            Single booted on both my laptop and desktop, because NixOs covers every use case <br><br>
            Keep being yourself and stay awesome <3 ⨺⃝ <br><br>"
            link="https://github.com/catboylei/Nixanthropy"
    />

    <Project
            src="/showcases/GregUtils.png"
            align="start"
            title="Greg Utils"
            desc="Minecraft mod designed for use on the Wynncraft server, with various QoL features
            for the TNA raid <br><br>
            For now it mainly just has a cool config gui and 1 feature but surely one day... <br><br>"
            link="https://github.com/catboylei/Greg-Utils"
    />

    <Project
            src="/showcases/LiveMajinReaction.png"
            align="end"
            title="Live Majin Reaction"
            desc="Another unfinished Minecraft mod that aims to improve your Wynncraft experience by having
            Sovereign Majin Thalas react to everything you do<br><br>
            Yet another mod with a cool gui but no actual features yet what am i doing <br><br>"
            link="https://github.com/catboylei/LiveMajinReaction"
    />

    <Project
            src="/showcases/fluffypaws.dev.png"
            align="start"
            title="fluffypaws.dev"
            desc="This is the website you are on !<br><br>
            Written in Astro/Svelte, showcases my projects, an about me and maybe eventually a blog <br><br>"
            link="https://github.com/catboylei/fluffy-paws.dev"
    />

    <Project
            src="/showcases/SimpleWifi-rs.png"
            align="end"
            title="SimpleWifi-rs"
            desc="Rust TUI wrapper on nmcli, aiming to cover the basic use cases of nmtui in a much prettier and enjoyable UI <br><br>"
            link="https://github.com/catboylei/fluffy-paws.dev"
    />

    <Separator text="Archived Projects"/>

    <Project
            src="/showcases/CatboyAddons-ct.png"
            align="start"
            title="CatboyAddons-ct"
            desc="Minecraft CT module for Hypixel Skyblock dungeons, had a lot of really cool features and
            was the best dungeon ct addon out there ngl <br><br>
            Didnt survive Hypixel moving past 1.8.9 <br><br>"
            link="ttps://github.com/catboylei/CatboyAddons-ct"
    />
</div>

<style>
    .top {
        display: flex;
        flex-direction: column;
        width: 100%;
        padding: 2.4vh;
        align-items: center;
        animation: fadeSlideUp 0.6s ease-out;
    }

    @keyframes fadeSlideUp {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .top > * {
        opacity: 0;
        animation: fadeSlideUp 0.5s ease-out forwards;
    }
    .top > *:nth-child(1) { animation-delay: 0.05s; }
    .top > *:nth-child(2) { animation-delay: 0.15s; }
    .top > *:nth-child(3) { animation-delay: 0.25s; }
    .top > *:nth-child(4) { animation-delay: 0.35s; }
    .top > *:nth-child(5) { animation-delay: 0.45s; }
    .top > *:nth-child(6) { animation-delay: 0.55s; }

    .text {
        color: var(--color);
        transition: color 0.25s ease;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        text-align: center;
        font-size: 2.2vh;
        font-weight: 700;
        margin-bottom: 2vh;
    }

    .text:hover {
        color: var(--hover-color)
    }

    .desc {
        font-size: 1.8vh;
    }
</style>