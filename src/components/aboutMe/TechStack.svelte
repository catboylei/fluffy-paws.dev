<script lang="ts">
    import {theme} from '../../constants.svelte.ts';

    const topRow = [
        {icon: '', href: 'https://rust-lang.org/'},
        {icon: '', href: 'https://www.typescriptlang.org/'},
        {icon: '', href: 'https://kotlinlang.org/'},
        {icon: '', href: 'https://www.latex-project.org/'},
        {icon: '', href: 'https://svelte.dev/'},
    ];

    const botRow = [
        {icon: '󱄅', href: 'https://nixos.org/'},
        {icon: '', href: 'https://fedoraproject.org/'},
        {icon: '', href: 'https://fedoraproject.org/coreos/'},
        {icon: '', href: 'https://neovim.io/'} // todo switch to helix
    ];
</script>

<div
        class="links"
        style:--fg={theme.fg}
        style:--fg-focused={theme.fg_focused}
>
    <span class="links-title">Stuff I use:</span>
    <div class="link-row-container">
        {#each topRow as { icon, label, href }}
            <a {href} class="link-row" target="_blank" rel="noopener noreferrer" aria-label={label}>
                <span class="icon">{icon}</span>
            </a>
        {/each}
    </div>
    <div class="link-row-container">
        {#each botRow as { icon, label, href }}
            <a {href} class="link-row" target="_blank" rel="noopener noreferrer" aria-label={label}>
                <span class="icon">{icon}</span>
            </a>
        {/each}
    </div>

</div>


<style>
    .links {
        display: flex;
        flex-direction: column;
        gap: 8px;
        align-items: center;
    }
    .links-title {
        color: var(--fg);
        transition: color 0.25s ease;
        font-family: 'SpaceGrotesk', monospace;
        font-size: 16px;
        font-weight: 700;
    }
    .link-row-container {
        display: flex;
        flex-direction: row;
        gap: 8px;
    }
    .links:hover .links-title {
        color: var(--fg-focused);
    }
    .link-row {
        color: var(--fg);
        text-decoration: none;
        transition: color 0.25s ease;
    }
    .link-row:hover {
        color: var(--fg-focused);
    }
    .icon {
        font-family: NerdFonts, monospace;
        font-size: 32px;
        text-align: center;
        padding-right: 4px;
        padding-left: 4px;
    }
</style>