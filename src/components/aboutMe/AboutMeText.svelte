<script>
    import {theme} from "../../constants.svelte.ts";
</script>

<div class="top"
        style:--color={theme.fg}
        style:--hover-color={theme.fg_focused}
>
    <p class="text">
        Hi ! I'm lei <span class="dim">(it/any)</span> :3 <br><br>
        I'm a dev* and CS student that spends most <br> of its free time working on random projects, <br> and is slightly obsessed by linux and trains <br>
        Hire me pls thanks <br><br>

        <span class="dim">* kinda mediocre one but i make cool stuff <br> sometimes soo</span>
    </p>
</div>

<style>
    .top {
        color: var(--color);
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-left: 2vh;
        padding-right: 2vh;
        text-align: center;
        font-weight: 700;
        transition: color 0.25s ease;
        max-height: 30vh;
        text-wrap: nowrap;
    }

    .top:hover {
        color: var(--hover-color);
    }

    .dim {
        opacity: 0.6;
    }

    .text {
        font-size: 1.8vh;
    }
</style>