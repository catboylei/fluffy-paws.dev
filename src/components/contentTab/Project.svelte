<script>
    import {theme} from "../../constants.svelte.ts";

    const { src, align, title, desc, link} = $props()

    const align_trans = ((align === "start") ? "left" : "right");
</script>

<div
        class="top"
        style:--color={theme.fg}
        style:--hover-color={theme.fg_focused}
        style:--align={align}
        style:--align-trans={align_trans}
        id={title}
>
    {#if (align === "start")}
        <img
                {src}
                alt={src}
        />
    {/if}

    <div class="text">
        <div class="text title">{title}</div>
        {@html desc}
        <a class="link" href={link} target="_blank" rel="noopener noreferrer">Check it out on GitHub </a>
    </div>

    {#if (align === "end")}
        <img
                {src}
                alt={src}
        />
    {/if}
</div>

<style>
    .top {
        display: flex;
        align-items: center;
        margin-top: 2vh;
        width: 90%;
        justify-content: var(--align);
    }

    .text {
        text-align: var(--align);
        max-width: 60vh;
        color: var(--color);
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        font-size: 1.8vh;
        font-weight: 700;
        transition: color 0.25s ease;
    }

    .top:hover .text {
        color: var(--hover-color)
    }

    img {
        display: block;
        object-fit: cover;
        border-style: solid;
        border-width: 0.3vh;
        border-color: var(--border-color);
        transition: border-color 0.25s ease;
        width: 50vh;
        height: 30vh;
        border-radius: 1vh;
        margin-right: 2vh;
        margin-left: 2vh;
    }
    .top:hover img {
        border-color: var(--hover-border);
    }

    .title {
        font-size: 2.2vh;
        margin-bottom: 2vh;
    }

    .link {
        text-decoration: none;
        color: var(--color);
        transition: color 0.25s ease, background-size 0.25s ease;
        background-repeat: no-repeat;
        background-image: linear-gradient(currentColor, currentColor);
        background-size: 0 0.3vh;
        background-position: var(--align-trans) bottom;
        padding-bottom: 0.3vh;
    }

    .link:hover {
        color: var(--hover-color);
        background-size: 100% 0.3vh;
    }

</style>