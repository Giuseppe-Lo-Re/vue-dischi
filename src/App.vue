<template>
  <div id="app">
    
    <PageHeader />

    <!-- Main -->
    <main>
      <PageProductList />
    </main>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";
import PageProductList from "./components/PageProductList.vue";

export default {
  name: 'App',
  components: {
    PageHeader,
    PageProductList,
  }
}
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';
</style>
