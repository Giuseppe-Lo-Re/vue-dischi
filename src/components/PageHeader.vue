<template>
  <header>
    
    <!-- Logo -->
    <div class="img-wrapper">
      <img src="../assets/img/logo.png" alt="spotify-logo">
    </div>
  </header>
</template>

<script>
export default {
    name: "PageHeader"
}
</script>

<style lang="scss" scoped>
@import '../style/common';
@import '../style/variables';

header {
  height: 70px;
  background-color: $secondary_color;

  .img-wrapper {
    padding: 15px;

    img {
      width: 40px;
      cursor: pointer;
    }
  }
}
</style>