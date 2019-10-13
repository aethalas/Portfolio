<template>
  <header>
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
  header {
    padding: 20px 0;
    text-align: left;
  }
</style>