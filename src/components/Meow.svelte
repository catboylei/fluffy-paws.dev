<script lang="ts">
    import {theme} from "../constants.svelte.ts"

    const meows = ["mrwo", "mrrra", "mrroaw", "purrr", "meow :3", "mrawr", "rawr"];
    let mip = $state("mrap");

    function randomize() {
        mip = meows[Math.floor(Math.random() * meows.length)];
        console.log($state.snapshot(mip));
    }

</script>

<button
        class="button"
        onclick={randomize}
        style:background-color={theme.bg}
        style:color={theme.fg}
>
    {mip}
</button>

<style>
    .button {
        height: 40px;
    }
</style>