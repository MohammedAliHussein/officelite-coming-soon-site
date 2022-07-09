<script>
    import { fade } from "svelte/transition";
    import { circOut } from "svelte/easing";
    import { onMount } from "svelte";

    let ready = false;
    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <h3 in:fade={{delay: 1000, duration: 1000, easing: circOut}}>officelite</h3>
{/if}

<style lang="scss">
    @import "../scss/theme.scss";

    h3 {
        @include H3;
        color: $DARK_NAVY;
    }
</style>