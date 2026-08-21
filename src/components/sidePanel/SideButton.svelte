<script>
import {theme} from "../../constants.svelte.ts";
import { slide } from 'svelte/transition';
const {button, children} = $props();
let isOpen = $state(button.title === "My Projects")

function handleClicked() {
    isOpen = !isOpen;
}
</script>

<div class="side-button">
    <button
            style:--color={theme.fg}
            style:--hover-color={theme.fg_focused}
            onclick={handleClicked}
    >
        {button.title}
        <span class="icon" style:transform={(isOpen) ? "rotate(90deg)" : ""}></span>
    </button>
    {#if isOpen}
        <div class="children" style:--side-color={theme.greyed_out} transition:slide>{@render children?.()}</div>
    {/if}
</div>

<style>
    button {
        border-width: 0;
        display: flex;

        width: fit-content;
        white-space: nowrap;

        margin-bottom: 4px;

        font-size: 16px;
        font-weight: 700;
        font-family: SpaceGrotesk, monospace;

        color: var(--color);

        background-color: transparent;

        transition: color 0.25s ease;
    }

    button:hover {
        color: var(--hover-color)
    }

    .icon {
        margin-left: 3px;
        display: block;
        height: 20px;
        width: 20px;
        mask: url('/icons/theshape.svg') no-repeat center / contain;
        -webkit-mask: url('/icons/theshape.svg') no-repeat center / contain;
        background-color: CurrentColor;
        transition: background-color 0.25s ease, transform 0.25s ease;
    }

    .side-button {
        display: flex;
        flex-direction: column;
        width: fit-content;

        margin-right: 12px;
        margin-left: 12px;
        margin-bottom: 12px;
    }

    .children {
        border-left: 2px solid var(--side-color);
        margin-left: 10px;
    }
</style>