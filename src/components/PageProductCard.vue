<template>
  <div>
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
    width: calc((100% / 5)); 
    padding: 10px;

    .product-card {
        background-color: $secondary_color;
        padding: 20px;
    }

    .title,
    .author,
    .year {
        text-align: center;
    }

    .title {
        color: white;
        padding-block: 10px;
    }

    .author,
    .year {
        color: $tertiary_color;
    }

    .img-wrapper {
        
        img {
            width: 100%;
            object-fit: cover; 
        }
    }
}


</style>