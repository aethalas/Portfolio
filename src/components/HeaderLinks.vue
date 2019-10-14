<template>
  <div class="about-me">
    <b-nav>
      <img src="../assets/face.png" alt="Jonny">
      <b-nav-item href="http://www.twitter.com/JonnyHTyson" target='_blank'>Twitter</b-nav-item>
      <b-nav-item href="https://github.com/aethalas" target='_blank'>GitHub</b-nav-item>
      <b-nav-item href="https://www.linkedin.com/in/jonnytyson/" target='_blank'>LinkedIn</b-nav-item>
      <b-nav-item href="http://www.fluffandhowl.com" target='_blank'>Fluff & Howl</b-nav-item>
      <b-nav-item href="mailto:aescencian@gmail.com" target='_blank'><i class="material-icons">email</i></b-nav-item>
    </b-nav>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
  img {
    width: 2.5vw;
  }

  a {
    display: inline-block;
    font-weight: bold;
    color: #4caf50;
    margin-left: 25px;
    font-size: 1vw;
    position: relative;
    text-decoration: none;
    text-shadow: 2px 2px 4px #000000;
  }

  a:hover {
    color: #2f6a31;
  }

   @media (max-width: 1400px) {
    img {
      margin-left: 2vw;
      margin-top: 1vw;
      margin-bottom: 1vw;
      width: 5%;
    }

    a {
      font-size: 3vw;
      margin-left: 0px;
    }
  }
</style>