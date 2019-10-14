<template>
  <div class="portfolio-about-me">
  <b-jumbotron fluid="false" bg-variant="none" text-variant="none" border-variant="none">
    <template v-slot:header>Jonathon H. Tyson</template>

    <template v-slot:lead>
      <h2>Software Engineer, Indie Game Developer, Web Developer</h2>
    </template>

  </b-jumbotron>
  </div>
</template>

<script>
</script>

<style scoped>
  @import url("https://fonts.googleapis.com/css?family=Ubuntu");
  @import url('https://fonts.googleapis.com/css?family=Signika&display=swap');
  @import url("https://fonts.googleapis.com/css?family=Rubik");
  @import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro:200,300");
  @import url('https://fonts.googleapis.com/css?family=Exo:400,700');

  .jumbotron {
    background-color:transparent !important;
    border:transparent !important;
    margin:0px !important;
  }

  .portfolio-about-me {
    text-align: center;
    display: inline-block;
    position: relative;
    text-align: center;
    width: 1400px;
  }

  img {
    width: 9vw;
    margin-top: 1vw;
    margin-bottom: 1vw;
  }

  h1 {
    font-family: 'Exo', sans-serif;
    font-weight: bold;
    text-align: center; 
    color: #505a55;
    font-size: 2.1vw;
    text-shadow: 2px 2px 4px #46c17b;
  }

  h2 {
    font-family: 'Exo', sans-serif;
    text-align: center;
    color: #333333;
    font-size: 1vw;
    text-shadow: 2px 2px 4px #46c17b;  
  }

 @media (max-width: 1400px) {
    .portfolio-about-me {
      width: 100%;
    }

    h1 {
      font-size: 4vw;
    }
    
    h2 {
      font-size: 2vw;
    }

    p {
      font-size: 3vw;
    }

    img {
      margin-left: 2vw;
      margin-top: 1vw;
      margin-bottom: 1vw;
      width: 15%;
    }
 }
</style>