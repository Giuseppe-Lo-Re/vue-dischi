<template>
  <div id="app">
    
    <PageHeader />

    <!-- Main -->
    <main>
      
    </main>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";

export default {
  name: 'App',
  components: {
    PageHeader,
    
  }
}
</script>

<style lang="scss">
@import './style/common';
@import './style/variables';

main {
  background-color: $main_color;
}

</style>
