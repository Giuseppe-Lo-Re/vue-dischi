<template>
  <div>
    <div class="product-card-container">
        <div class="product-card">

            <!-- Image -->
            <div class="img-wrapper">
                <img src="../assets/img/bad.jpeg" alt="">
            </div>

            <!-- Title -->
            <h3 class="title">
                BAD
            </h3>

            <!-- Artist -->
            <div class="artist">
                Michael Jackson
            </div>

            <!-- Year -->
            <div class="year">
                1987
            </div>
            
        </div>

    </div>
  </div>
</template>

<script>
export default {
    name: "PageProductCard",

}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';

.product-card-container {
    width: calc((100% / 5));

    .title,
    .artist,
    .year {
        text-align: center;
    }

    .title {
        color: white;
        padding-block: 10px;
    }

    .artist,
    .year {
        color: $tertiary_color;
    }

    .img-wrapper {
        // TEST
        width: 200px;
    }
}


</style>