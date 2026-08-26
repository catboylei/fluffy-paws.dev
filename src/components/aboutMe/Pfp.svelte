<script lang="ts">
    import {theme} from "../../constants.svelte.ts";
</script>

<img
        src="/icons/pfp.jpg"
        alt="pfp"
        class="themed-image"
        style:--border-color={theme.fg}
        style:--hover-border={theme.fg_focused}
/>

<style>
    .themed-image {
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
    }
    .themed-image:hover {
        border-color: var(--hover-border);
    }
</style>