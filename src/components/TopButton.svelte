<script>
    import {theme} from "../constants.svelte.ts";
    const {button} = $props();

    function openPage() {
        window.location.href = button.link
    }
</script>

<button class="button"
        onclick={openPage}

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
        background-size: 0 4px;
    }

    .button:hover {
        background-size: 100% 4px;
    }
</style>