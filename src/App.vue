<template>
  <div id="app" class="app">
    <div class="header-style">
      <Header />
    </div>
    <About />
    <div class="alternate-style">
      <Projects />
    </div>
    <div class="footer-style">
      <Footer />
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import About from './components/About.vue'
  import Projects from './components/Projects.vue'
  import Footer from './components/Footer.vue'

  export default {
    name: 'portfolio',
    components: {
      Header,
      About,
      Projects,
      Footer
    }
  }
</script>

<style>
  @import url("https://fonts.googleapis.com/icon?family=Material+Icons");
  @import url("https://fonts.googleapis.com/css?family=Rubik");
  
  * {
    box-sizing: border-box;
  }

  body {
    background: #ffffff;
    margin: 0;
  }

  .about-me {
    max-width: 1400px;
    margin: 0 auto;
  }

  .max-width {
    max-width: 1400px;
    margin: 0 auto;
    font-size: 0;
  }

  .app {
    font-family: 'Rubik', sans-serif;
    text-align: center;
    color: #000000;
  }

  .header-style {
    background: #363b40;
  }

  .alternate-style {
    background: #e5e7e7;
    padding: 1vw;
  }

  .blog-style {
    background: #e5e7e7;
    padding: 1vw;
  }

  .footer-style {
    background: #363b40;
  }
</style>
