<script>
    import { fly } from "svelte/transition";
    import { circInOut } from "svelte/easing";
    import { onMount } from "svelte";

    function getFly(delay) {
        return {
            y: 10,
            delay: delay,
            duration: 400,
            easing: circInOut
        }
    }

    let ready = false;
    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="header-graphic">
        <div class="vertical-graphics">
            <img in:fly={getFly(1000)} id="graphic-1" src="mobile/graphic-1.svg" alt="">
            <img in:fly={getFly(1300)} id="graphic-2" src="mobile/graphic-2.svg" alt="">
        </div>
        <img in:fly={getFly(1600)} id="graphic-3" src="mobile/graphic-3.svg" alt="">
        <img id="graphic-4" src="mobile/electrons.svg" alt="">
    </div>
{/if}

<style lang="scss">
    @import "../scss/mixins.scss";

    .header-graphic {
        @include FLEX_CENTER_ROW;
        margin-top: 30px;
        width: 100%;
        padding-top: 30px;
    }

    .vertical-graphics {
        @include FLEX_CENTER_COLUMN;
        margin: 20px 9px 0px 0px;
    }

    #graphic-1 {
        margin-bottom: 11px;
        filter: drop-shadow(0px 50px 50px #4b5c9a54);
    }

    #graphic-3 {
        filter: drop-shadow(0px 50px 50px #4b5c9a35);
    }

    #graphic-4 {
        position: absolute;
        top: 0;
        transform: translateY(-10px);
        z-index: -1;
    }
</style>