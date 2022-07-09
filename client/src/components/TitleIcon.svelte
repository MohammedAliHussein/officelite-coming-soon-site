<script>
    import { fly } from "svelte/transition";
    import { circOut } from "svelte/easing";
    import { onMount } from "svelte";

    function getFly(x) {
        return {
            duration: 800,
            x: x,
            easing: circOut,
            opacity: 1
        }
    }

    let ready = false;
    onMount(() => {
        ready = true;
    });
</script>

{#if ready}
    <div class="title-icon">
        <div class="left-circle" in:fly={getFly(7.5)}></div>
        <div class="right-circle" in:fly={getFly(-7.5)}></div>
        <div class="overlap"></div>
    </div>
{/if}

<style lang="scss">
    @import "../scss/mixins.scss";
    @import "../scss/theme.scss";

    .title-icon {
        @include FLEX_CENTER_ROW;
        position: relative;
        width: 45px;
        margin-right: 9px;
    }

    .left-circle, .right-circle, .overlap {
        position: absolute;
        width: 30px;
        height: 30px;
        background-color: $BLUE;
        border-radius: 100%;
    }

    .left-circle, .overlap {
        transform: translateX(-7.5px);
    }

    .right-circle {
        transform: translateX(7.5px);
    }

    .overlap {
        background-color: $LIGHT_BLUE;
        animation: grow 0.5s cubic-bezier(0, 0.55, 0.45, 1);
        clip-path: circle(50% at 100%);
    }

    @keyframes grow {
        0% {
            clip-path: circle(15% at 100%);
            opacity: 0;
        }
        100% {
            clip-path: circle(50% at 100%);
            opacity: 1;
        }
    }
</style>