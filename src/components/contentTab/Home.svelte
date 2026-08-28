<script>
    import {aboutMeOpen, sidePanelOpen, theme} from "../../constants.svelte.ts";
    import {onDestroy, onMount} from "svelte";
    import SplashText from "./SplashText.svelte";

    function openProjects() {
        window.location.href = '/projects'
    }

    let containerEl;
    let imgEl;

    let x = $state(0);
    let y = $state(0);
    let rotation = $state(0);
    let dx = 2.2;
    let dy = 1.2;
    const rotationSpeed = 0.15;

    let rafId;

    function tick() {
        if (containerEl && imgEl) {
            const maxX = containerEl.clientWidth - imgEl.clientWidth;
            const maxY = containerEl.clientHeight - imgEl.clientHeight;

            x += dx;
            y += dy;

            if (x <= 0 || x >= maxX) {
                dx *= -1;
                x = Math.max(0, Math.min(x, maxX));
            }
            if (y <= 0 || y >= maxY) {
                dy *= -1;
                y = Math.max(0, Math.min(y, maxY));
            }

            rotation += rotationSpeed;
            if (rotation >= 360) rotation -= 360;
        }
        rafId = requestAnimationFrame(tick);
    }

    onMount(() => {
        rafId = requestAnimationFrame(tick);
    });

    onDestroy(() => {
        if (typeof cancelAnimationFrame !== 'undefined') {
            cancelAnimationFrame(rafId);
        }
    });
</script>

<div class="thestackerrr"
     style:--hover-color={theme.fg_focused}
     style:--color={theme.fg}
     bind:this={containerEl}
>
    <img class="nixos" src="/icons/nixos.png" alt="" bind:this={imgEl}
         style:transform="translate({x}px, {y}px) rotate({rotation}deg)"/>

    <div
            class="top"
    >

        <div class="text">
            Hello there !
        </div>
        <div class="splash-wrapper">
            <div class="desc text">
                Welcome to my little internet den :3 ! I share random projects and do fun stuff here. Look around :>
            </div>
            <SplashText class="splash"/>
        </div>
        <div class="desc text">
            Something catch your eye, or got feedback? Hit me up on any platform in my about me. I don't bite... usually
            :3
        </div>
        <div class="text">
            About This Website
        </div>
        <div class="desc text">
            I showcase my public GitHub projects here and add extra info about what I do. It's also my playground for
            webdev with Astro/Svelte !<br>
            I host a few personal / for other people docs here too, like the ones under Private <br>
            A blog might show up eventually, for my random opinions :p
        </div>

        <button class="projects text" onclick={openProjects}>
            Check out my projects !
        </button>

    </div>

    <div class="thisismebtw">
        <div class="desc text">
            this is me btw ---->
        </div>

        <img
                class="me"
                src="/me.jpg"
                alt="me"
                style:--border-color={theme.fg}
                style:--hover-border={theme.fg_focused}
        />
    </div>

    {#if !sidePanelOpen.value}
        <div class="corner-tag corner-tag-left">
            <span class="arrow">↖</span>
            <span>Now with a navigation tab !</span>
        </div>
    {/if}

    {#if !aboutMeOpen.value}
        <div class="corner-tag corner-tag-right">
            <span>Look it's an about me tab !</span>
            <span class="arrow">↗</span>
        </div>
    {/if}

    <video
            class="bg-video"
            src="/hyfetch.mp4"
            autoplay
            loop
            muted
            playsinline
    ></video>
</div>


<style>
    .top {
        display: flex;
        flex-direction: column;
        width: 100%;
        padding: 2.4vh;
        align-items: center;
        max-width: 50vw;
        height: 100%;
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

    .top > *:nth-child(1) {
        animation-delay: 0.05s;
    }

    .top > *:nth-child(2) {
        animation-delay: 0.15s;
    }

    .top > *:nth-child(3) {
        animation-delay: 0.25s;
    }

    .top > *:nth-child(4) {
        animation-delay: 0.35s;
    }

    .top > *:nth-child(5) {
        animation-delay: 0.45s;
    }

    .top > *:nth-child(6) {
        animation-delay: 0.55s;
    }

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


    .thisismebtw {
        position: absolute;
        bottom: 1vh;
        right: -1vh;
        display: flex;
        align-items: center;
        gap: 2vh;
        z-index: 5;
        animation: fadeSlideUp 0.5s ease-out forwards;
        animation-delay: 0.65s;
        opacity: 0;
    }

    .me {
        display: block;
        object-fit: cover;
        border-style: solid;
        border-width: 0.3vh;
        border-color: var(--border-color);
        transition: border-color 0.25s ease;
        width: 20vh;
        height: 30vh;
        border-radius: 1vh;
        margin-right: 2vh;
        margin-left: 1vh;
        opacity: 0.85;
    }

    .me:hover {
        border-color: var(--hover-border);
        transform: scale(1.03) rotate(-1deg);
    }

    .projects {
        background-color: transparent;
        background-repeat: no-repeat;
        background-position: center bottom;
        background-image: linear-gradient(currentColor, currentColor);
        transition: background-size 0.25s ease;
        background-size: 0 0.3vh;
        border-width: 0;
    }

    .projects:hover {
        background-size: 80% 0.3vh;
    }

    .thestackerrr {
        position: relative;
        display: flex;
        width: 100%;
        height: 100%;
        justify-content: center;
        align-items: flex-start;
    }

    .nixos {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 0;
        pointer-events: none;
        width: 20vh;
        height: 20vh;
        opacity: 0.4;
    }

    .bg-video {
        position: absolute;
        bottom: 1vh;
        left: 1vh;
        width: 55vh;
        height: auto;
        z-index: 5;
        border-style: solid;
        border-width: 0.3vh;
        border-radius: 1vh;
        border-color: var(--border-color);
        transition: border-color 0.25s ease;
        opacity: 0;
        animation: fadeSlideUp 0.5s ease-out forwards;
        animation-delay: 0.65s;
    }

    .bg-video:hover {
        border-color: var(--hover-border);
        transform: scale(1.03) rotate(-1deg);
    }

    .splash-wrapper {
        position: relative;
        display: inline-block;
    }

    .corner-tag {
        position: absolute;
        top: 1vh;
        z-index: 6;
        display: flex;
        align-items: center;
        gap: 0.4vh;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        font-size: 1.6vh;
        font-weight: 600;
        color: var(--color);
        opacity: 0.75;
        pointer-events: none;
        white-space: nowrap;
    }

    .corner-tag-left {
        left: 6vh;
    }

    .corner-tag-right {
        right: 6vh;
    }

    .arrow {
        font-size: 1.6vh;
        line-height: 1;
        animation: nudge 1.6s ease-in-out infinite;
    }

    .corner-tag-left .arrow {
        transform-origin: bottom right;
    }

    .corner-tag-right .arrow {
        transform-origin: bottom left;
    }

    @keyframes nudge {
        0%, 100% {
            transform: translate(0, 0);
        }
        50% {
            transform: translate(-2px, -2px);
        }
    }
</style>
