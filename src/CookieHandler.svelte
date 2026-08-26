<script lang="ts">
    import {sidePanelOpen, aboutMeOpen, isHydrated} from './constants.svelte.ts';

    const SIDE_COOKIE = 'sidePanelOpen';
    const ABOUT_COOKIE = 'aboutMeOpen';

    $effect.root(() => {
        const match1 = document.cookie.match(new RegExp(`(?:^|; )${SIDE_COOKIE}=([^;]*)`));
        if (match1) {
            sidePanelOpen.value = match1[1] === 'true';
        }

        const match2 = document.cookie.match(new RegExp(`(?:^|; )${ABOUT_COOKIE}=([^;]*)`));
        if (match2) {
            aboutMeOpen.value = match2[1] === 'true';
        }

        // this is evil btw i hate this but it works so im not gonna touch it
        requestAnimationFrame(() => {
            requestAnimationFrame(() => {
                isHydrated.value = true;
            });
        });

        $effect(() => {
            document.cookie = `${SIDE_COOKIE}=${sidePanelOpen.value}; path=/; max-age=${60 * 60 * 24 * 365}; SameSite=Lax`;
            document.cookie = `${ABOUT_COOKIE}=${aboutMeOpen.value}; path=/; max-age=${60 * 60 * 24 * 365}; SameSite=Lax`;
        });
    });
</script>
