<template>
  <div class="project" v-on:mouseover="isCursorHovering = true" v-on:mouseleave="isCursorHovering = false">
    <div class="project-title" v-if="isCursorHovering"></div>
    <div class="project-title" v-else><h1>{{data.name}}</h1></div>
    <div class="project-image" v-if="isCursorHovering"><ProjectModal :data="data"/></div>
    <div class="project-image" v-else><img :src="getPortfolioImg('png')"></div>
  </div>
</template>

<script>
  import ProjectModal from './ProjectModal.vue'

  export default {    
    components: {
      ProjectModal
    },

    props: {
      data: Object,
      default: {
        name: '',
        img:  '',
        youtube: '',
        github: '',
        desc: '',
        about: ''
      }
    },

    methods: {
      getPortfolioImg: function (type) {
        return require("../assets/" + this.data.img + '.' + type);
      },

      getPortfolioURL: function (projectURL) {
        window.location.href = projectURL;
      }
    },

    data: function () {
      return {
        isCursorHovering: false
      }
    }
  }
</script>

<style scoped>
  img {
    width: 100%;
    display: block;
  }

  h1 {
    color: #5cb85c;
    font-size: 2.5vw;
    text-shadow: 2px 2px 4px #000000;
    max-width: 100%;
  }

  h2 {
    color: #449d44;
    font-size: 1vw;
    text-shadow: 2px 2px 4px #000000;
    max-width: 100%;
    opacity: 0.5;
  }

  a {
    display: inline-block;
    font-weight: bold;
    color: #428bca;
    font-size: 1vw;
    position: relative;
    text-decoration: none;
    text-shadow: 2px 2px 4px #000000;
  }

  a:hover {
    color: #ffffff;
  }

  .button {
    font-family: 'Rubik', sans-serif;
    font-size: 1vw;
    background: none;
    text-shadow: 2px 2px 4px #000000;
    border: none;
    color: #428bca;
    padding: 0.3vw 1vw;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    margin-top: 25px;
    margin: 4px 2px;
    padding: 15px;
    cursor: pointer;
    -webkit-transition-duration: 0.4s;
    transition-duration: 0.4s;
    border-radius: 15px;
    opacity: 0.5;
    border: 2px solid #428bca;
  }

  .button:hover {
    box-shadow: 0 5px 10px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
    opacity: 1;
    background-color: #428bca;
    color: #ffffff;
  }

  .project {
    width: 50%;
    display: inline-block;
    position: relative;
    text-align: center;
    color: white;
  }

  .project-title {
    font-family: 'Rubik', sans-serif;
    color: #ffffff;
    font-size: 1vw;
    text-shadow: 2px 2px 4px #000000;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  
  .project-image {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }

  @media (max-width: 1200px) {
    .project {
      width: 100%;
    }

    h1, h2, h3 {
      font-size: 9vw;
    }
  }
</style>