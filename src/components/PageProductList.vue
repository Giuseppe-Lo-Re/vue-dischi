<template>
  <div class="container">

    <!-- Select Menù-->
    <div class="select">
        <PageSelect @selectedGenre="changeSelect" />
    </div>
     
    <!-- Album List -->
    <div class="products-list">
        <PageProductCard 
            v-for="(album,index) in filteredProductList" 
            :key="index"
            :productDetails="album" />
    </div>
  </div>
</template>

<script>
import PageProductCard from "./PageProductCard.vue";
import PageSelect from "./PageSelect.vue";
import axios from "axios";

export default {
name: "PageProductList",
components: { 
    PageProductCard,
    PageSelect
},
data() {
        return {
            url:"https://flynn.boolean.careers/exercises/api/array/music",
            albumList: [],
            selectedGenre : '',
        }
    },
    created() {
        this.getAlbums();
    },
    computed: {
        filteredProductList() {
            if (this.selectedGenre === 'all') {
                return this.albumList
            } else {
                return this.albumList.filter((item) => {
                    return item.genre.includes(this.selectedGenre)
                })
            }
        }
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
        },
        changeSelect(selection) {
            this.selectedGenre = selection;
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';

.select {
    padding: 20px 10px 10px 10px;
}
.products-list {
    display: flex;
    flex-wrap: wrap;
    gap: $main_card_gap;
    margin-top: 50px;
}
</style>