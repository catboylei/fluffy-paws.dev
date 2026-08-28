<script>
    import {onMount} from "svelte";
    import {theme} from "../../constants.svelte.ts";

    const messages = [
        "mrrp",
        "probably breaking something rn",
        "powered by spite and caffeine",
        "the css horrors...",
        "astro devs hate this 1 trick",
        "i use nixos btw",
        "now with 200% more caffeine",
        "mrraow mrrp purr meow :3",
        "my paws are big and soft",
        "so so so much css",
        "\"it's 5am and im still fixing css\"",
        "tried to center a div, this is the result",
        "i might just be a cat...",
        "stay fucking awesome <33 ⨺⃝",
        "we stay silly :3 :3 :3 :3",
        "this homepage is 300 lines of terrible svelte btw"
    ];

    let current = $state(messages[Math.floor(Math.random() * messages.length)]);

    onMount(() => {
        const interval = setInterval(() => {
            let next;
            do {
                next = messages[Math.floor(Math.random() * messages.length)];
            } while (next === current); // avoid repeating the same one twice in a row
            current = next;
        }, 10000);

        return () => clearInterval(interval);
    });
</script>

<div class="splash-tag" style:--color={theme.fg}>
    {current}
</div>

<style>
    .splash-tag {
        position: absolute;
        top: -4vh;
        right: -6vh;
        z-index: 5;
        font-family: 'SpaceGrotesk', NerdFonts, monospace;
        font-weight: 700;
        font-size: 1.8vh;
        color: var(--color);
        transform-origin: center;
        animation: splashPulse 1.6s ease-in-out infinite;
        pointer-events: none;
        white-space: nowrap;
    }

    @keyframes splashPulse {
        0%, 100% {
            transform: scale(1) rotate(8deg);
        }
        50% {
            transform: scale(1.15) rotate(8deg);
        }
    }
</style>