<template>
    <div class="product-card-container">
        <div class="product-card">

            <!-- Image -->
            <div class="img-wrapper">
                <img :src="productDetails.poster" :alt="productDetails.title">
            </div>

            <!-- Title -->
            <h3 class="title">
                {{productDetails.title}}
            </h3>

            <!-- Author -->
            <div class="author">
                {{productDetails.author}}
            </div>

            <!-- Year -->
            <div class="year">
                {{productDetails.year}}
            </div>
        </div>
    </div>
</template>

<script> 
export default {
    name: "PageProductCard",
    props: {
        productDetails: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';

.product-card-container {
    width: calc((100% / 5) - $main_card_gap);
    padding: 10px;
    
    .product-card { 
        background-color: $secondary_color;
        padding: 20px;
        min-height: 300px;
    }

    .title,
    .author,
    .year {
        text-align: center;
    }

    .title {
        color: white;
        padding-top: 20px;
        padding-bottom: 10px;
        text-transform: uppercase;
    }

    .author,
    .year {
        color: $tertiary_color;
        font-size: 12px;
    }

    .img-wrapper {
        
        img {
            height: 130px;
        }
    }
}
</style>