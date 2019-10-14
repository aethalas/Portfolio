<template>
  <div style="padding-top: 150px;">
  <footer class="footer-style fixed-bottom">
    <FooterLinks />
  </footer>
  </div>
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
    width: 100%;
    padding: 15px 0;
  }

  @media (max-width: 1400px) {
    .footer-style {
      padding: 0px;
    }
   }
</style>