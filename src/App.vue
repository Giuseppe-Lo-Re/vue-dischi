<template>
  <div id="app">
    
    <PageHeader />

    <!-- Main -->
    <main>
      <!-- <PageSelect /> -->
      <PageProductList />
    </main>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";
import PageProductList from "./components/PageProductList.vue";
// import PageSelect from "./components/PageSelect.vue"

export default {
  name: 'App',
  components: {
    PageHeader,
    PageProductList,
    // PageSelect
  }
}
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';
</style>
