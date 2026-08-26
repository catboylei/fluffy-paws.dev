<script lang="ts">
	import { sidePanelOpen } from './constants.svelte.ts';

	const NAME = 'sidePanelOpen';

	$effect.root(() => {
		const match = document.cookie.match(new RegExp(`(?:^|; )${NAME}=([^;]*)`));
		if (match) sidePanelOpen.value = match[1] === 'true';

		$effect(() => {
			document.cookie = `${NAME}=${sidePanelOpen.value}; path=/; max-age=${60 * 60 * 24 * 365}; SameSite=Lax`;
		});
	});
</script>
