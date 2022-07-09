<script>
    import HeaderTitle from "../components/HeaderTitle.svelte";
</script>

<div class="header">
    <HeaderTitle />
    <!-- <HeaderGraphic /> -->
</div>

<style lang="scss">
    @import "../scss/mixins.scss";

    .header {
        @include FLEX_CENTER_ROW;
        width: 100%;
    }
</style>