<script>

</script>

<div class="header-graphic">
    <div class="vertical-graphics">
        <img id="graphic-1" src="/graphic-1.svg" alt="">
        <img id="graphic-2" src="/graphic-2.svg" alt="">
    </div>
    <img id="graphic-3" src="/graphic-3.svg" alt="">
</div>

<style lang="scss">
    @import "../scss/mixins.scss";

    .header-graphic {
        margin-top: 30px;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
    }

    img {
    }

    .vertical-graphics {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>