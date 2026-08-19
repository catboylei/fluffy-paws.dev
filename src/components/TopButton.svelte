<script>
    import {theme} from "../constants.svelte.ts";
    const {button} = $props();
    let isHovered = $state(false);

    function openPage() {
        window.location.href = button.link
    }
</script>

<button class="button"
        onclick={openPage}
        onmouseenter={() => isHovered = true}
        onmouseleave={() => isHovered = false}
        style:background-size={isHovered ? "100% 4px" : "0 4px"}

        style:color={theme.fg}
>
    {button.title}
</button>

<style>
    .button {
        border-width: 0;

        height: 40px;

        font-weight: bold;
        font-family: Monocraft, monospace;

        background-color: transparent;
        background-repeat: no-repeat;
        background-position: center bottom;
        background-image: linear-gradient(currentColor, currentColor);
        transition: background-size 0.25s ease;
    }
</style>