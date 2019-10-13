<template>
  <div class="about-me">
    <div class="portfolio-about-me"><img src="../assets/face.png" align="left">
    <h1>Jonathon H. Tyson</h1>
    <h2>Software Engineer, Indie Game Developer, Artist</h2></div>
  </div>
</template>

<script>
</script>

<style scoped>
  @import url("https://fonts.googleapis.com/css?family=Ubuntu");

  .portfolio-about-me {
    text-align: left;
    display: inline-block;
    position: relative;
    text-align: center;
    width: 100%;
  }

  img {
    width: 9vw;
    margin-top: 1vw;
    margin-bottom: 1vw;
  }

  h1 {
    font-family: 'Ubuntu', sans-serif;
    text-align: left; 
    color: #428bca;
    margin-top: 2.5vw;
    margin-left: 11vw;
    font-size: 1.5vw;
    text-shadow: 2px 2px 4px #d5d5d5;
  }

  h2 {
    font-family: 'Ubuntu', sans-serif;
    text-align: left;
    color: #333333;
    margin-top: 2.5vw;
    margin-left: 11vw;
    font-size: 1vw;
    text-shadow: 2px 2px 4px #d5d5d5;  
  }

 @media (max-width: 1400px) {
    h1 {
      font-size: 3vw;
      margin-top: 4vw;
      margin-left: 19vw;
    }
    
    h2 {
      font-size: 2vw;
      margin-top: 4vw;
      margin-left: 19vw;
    }

    img {
      margin-left: 2vw;
      margin-top: 1vw;
      margin-bottom: 1vw;
      width: 15%;
    }
 }
</style>