<template>
  <footer>
    <FooterLinks />
  </footer>
</template>

<script>
  import FooterLinks from './FooterLinks.vue'

  export default {
    components: {
      FooterLinks
    }
  }
</script>

<style scoped>
  footer {
    padding: 20px 0;
    text-align: left;
  }
</style>