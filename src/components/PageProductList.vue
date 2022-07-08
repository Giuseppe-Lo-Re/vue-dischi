<template>
  <div class="container">
    <div class="products-list">
        <PageProductCard />
    </div>

  </div>
</template>

<script>
import PageProductCard from "./PageProductCard.vue";

export default {
name: "PageProductList",
components: {
    PageProductCard
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