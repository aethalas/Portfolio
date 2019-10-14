<template>
  <header class="header-style">
    <HeaderLinks />
  </header>
</template>
 
<script>
  import HeaderLinks from './HeaderLinks.vue'

  export default {
    components: {
      HeaderLinks
    }
  }
</script>

<style scoped>
  .header-style {
    background: #363b40;
    width: 100%;
    padding: 15px 0;
  }
</style>