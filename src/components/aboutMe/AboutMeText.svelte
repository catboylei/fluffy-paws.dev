<script>
    import {theme} from "../../constants.svelte.ts";
</script>

<div class="top"
        style:--color={theme.fg}
        style:--hover-color={theme.fg_focused}
>
    <p>
        Hi ! I'm lei :3 <br><br>
        I'm a dev* and CS student that spends most of its free time working on random projects, and is slightly obsessed by linux and trains <br>
        Hire me pls thanks <br><br>

        <em>* kinda mediocre one but i make cool stuff sometimes soo</em>
    </p>
</div>

<style>
    .top {
        color: var(--color);
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-left: 24px;
        padding-right: 24px;
        text-align: center;
        font-weight: 700;
        transition: color 0.25s ease;
    }

    .top:hover {
        color: var(--hover-color);
    }
</style>