<template>
  <div class="container">
    <div class="products-list">
        <PageProductCard 
            v-for="(album,index) in albumList" 
            :key="index"
            :productDetails="album" />
    </div>

  </div>
</template>

<script>
import PageProductCard from "./PageProductCard.vue"; 
import axios from "axios";

export default {
name: "PageProductList",
components: { 
    PageProductCard
},
data() {
        return {
            url:"https://flynn.boolean.careers/exercises/api/array/music",
            albumList: []
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

.products-list {
    display: flex;
    flex-wrap: wrap;  
}
</style>