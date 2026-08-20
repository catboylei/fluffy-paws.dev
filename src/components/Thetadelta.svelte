<script>
    import {theme} from "../constants.svelte.ts";
    import {onMount} from "svelte";

    let degreesLeft = 0;
    let rotation = $state(0);

    function addRotations() {
        degreesLeft += 360
    }

    onMount(() => {
        let lastTime = performance.now();
        let rafId;

        function tick(now) {

            const elapsed = now - lastTime;
            lastTime = now;

            const factor = Math.pow(0.8, elapsed / 100);
            const delta = degreesLeft * (1 - factor);

            rotation += delta;
            degreesLeft -= delta;

            rafId = requestAnimationFrame(tick);
        }

        rafId = requestAnimationFrame(tick);

        return () => cancelAnimationFrame(rafId);
     })
</script>

<button aria-label="meow" onclick={addRotations}>
    <span style:--color={theme.fg} style:--hover-color={theme.fg_focused}
          style:transform={`rotate(${rotation}deg)`}></span>
</button>

<style>
    button {
        border-width: 0;
        background-color: transparent;
    }

    span {
        display: block;
        height: 40px;
        width: 40px;
        mask: url('/icons/thetadelta.svg') no-repeat center / contain;
        -webkit-mask: url('/icons/thetadelta.svg') no-repeat center / contain;
        background-color: var(--color);
        transition: background-color 0.25s ease;
        transform-origin: 50% 60%;
    }

    span:hover {
        background-color: var(--hover-color)
    }
</style>