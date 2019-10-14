<template>
  <div>
    <b-nav align="center">
      <b-nav-item active>© 2015-2020 <b>JonnyHTyson.com</b> All rights reserved.</b-nav-item>
      <b-nav-item href="http://www.niniloves.com" target='_blank'>Visit Niniloves.com</b-nav-item>
      <b-nav-item href="http://www.joyboxco.com" target='_blank'>Visit Joyboxco.com</b-nav-item>
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