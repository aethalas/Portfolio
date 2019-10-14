<template>
  <footer class="footer-style">
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
  .footer-style {
    background: #363b40;
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 15px 0;
  }
</style>