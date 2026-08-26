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
        border-width: 2px;
        border-color: var(--border-color);
        transition: border-color 0.25s ease;
        width: 200px;
        height: 300px;
        border-radius: 10px;
        margin-right: 24px;
        margin-left: 12px;
    }
    .themed-image:hover {
        border-color: var(--hover-border);
    }
</style>