<template>
  <div class="container">

    <div class="cards">
        <div class="filters">
            <Select @selectFilter="getSelected()"
                :filters="getGenres()"
                :filter-name="'genere'"/>
        </div>

    <div class="products-list">
        <PageProductCard 
            v-for="(album,index) in albumList" 
            :key="index"
            :productDetails="album" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import PageProductCard from "./PageProductCard.vue"; 
import Select from './PageSelect.vue';

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
    gap: $main_card_gap;
    margin-top: 50px;
}
</style>