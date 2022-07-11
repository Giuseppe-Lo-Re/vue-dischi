<template>
  <div class="container">

    <!-- Select Menù-->
    <div class="select">
        <PageSelect @selectedGenre="changeSelect()" />
    </div>
     
    <!-- Album List -->
    <div class="products-list">
        <PageProductCard 
            v-for="(album,index) in filteredProductList()" 
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
    // Lancia la funzione prima del caricamento del DOM
    created() {
        this.getAlbums();
    },
    computed: {
        // Filtra l'array degli album secondo la selezione dell'utente
        filteredProductList() {
            if (this.selectedGenre === 'all') {
                return this.albumList
            } else {
                return this.albumList.filter((item) => {
                    return item.genre.includes(this.selectedGenre)
                });
            }
        }
    },
    methods: {
        // Scarica l'array degli album attraverso una chiamata API
        getAlbums() {
            axios.get(this.url)
            .then((response) => {
                this.albumList = response.data.response;
            }) 
            .catch((err) => {
                 console.log("error", err);
            });
        },
        // Definisce la selezione dell'utente
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
}
</style>