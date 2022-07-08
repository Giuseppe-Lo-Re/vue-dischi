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
import axios from "axios";

export default {
    name: "PageProductCard",
    data() {
        return {
            url:"https://flynn.boolean.careers/exercises/api/array/music",
            albumlist: []
        }
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            axios.get(this.url)
            .then((response) => {
                this.albumList = response.data.response;
            }) 
            .catch((err) => {
                 console.log("error", err);
            });
        }
    }
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