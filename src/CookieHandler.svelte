<script lang="ts">
    import {sidePanelOpen, isHydrated} from './constants.svelte.ts';
    import {tick} from "svelte";

    const NAME = 'sidePanelOpen';

    $effect.root(() => {
        const match = document.cookie.match(new RegExp(`(?:^|; )${NAME}=([^;]*)`));
        if (match) {
            sidePanelOpen.value = match[1] === 'true';
        }

        // this is evil btw i hate this but it works so im not gonna touch it
        requestAnimationFrame(() => {
            requestAnimationFrame(() => {
                isHydrated.value = true;
            });
        });

        $effect(() => {
            document.cookie = `${NAME}=${sidePanelOpen.value}; path=/; max-age=${60 * 60 * 24 * 365}; SameSite=Lax`;
        });
    });
</script>
