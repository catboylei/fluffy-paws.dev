<script lang="ts">
    import { theme } from '../../constants.svelte.ts';

    const links = [
        { icon: '', label: 'GitHub', href: 'https://github.com/catboylei' },
        { icon: '', label: 'Discord', href: 'https://discord.com/users/catboylei' },
        { icon: '', label: 'Bluesky', href: 'https://bsky.social/about' }, // todo make a bsky account lol
        { icon: '', label: 'Steam', href: 'https://steamcommunity.com/id/catboylei/' },
    ];
</script>

<div
        class="links"
        style:--fg={theme.fg}
        style:--fg-focused={theme.fg_focused}
>
    {#each links as { icon, label, href }}
        <a {href} class="link-row" target="_blank" rel="noopener noreferrer" aria-label={label}>
            <span class="label">{label}</span>
            <span class="icon">{icon}</span>
        </a>
    {/each}
</div>

<style>
    .links {
        display: flex;
        flex-direction: column;
        gap: 1vh;
        align-items: end;
    }
    .link-row {
        display: flex;
        align-items: center;
        gap: 1vh;
        color: var(--fg);
        text-decoration: none;
        transition: color 0.2s ease;
    }
    .link-row:hover {
        color: var(--fg-focused);
    }
    .icon {
        font-family: NerdFonts, monospace;
        font-size: 1.5vh;
        text-align: center;
    }
    .label {
        font-family: 'SpaceGrotesk', monospace;
        font-size: 1.5vh;
        font-weight: 700;
    }
</style>