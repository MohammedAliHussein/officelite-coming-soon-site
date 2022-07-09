<script>
    import TitleText from "./TitleText.svelte";
    import TitleIcon from "./TitleIcon.svelte";
</script>

<div class="header-title">
    <TitleIcon />
    <TitleText />
</div>

<style lang="scss">
    @import "../scss/mixins.scss";

    .header-title {
        @include FLEX_CENTER_ROW;
    }
</style>