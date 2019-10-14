<template>

  <div class="project">
    <b-modal v-model="modalShow" id="modal-1" size="xl" hide-footer hide-header-close no-close-on-esc no-close-on-backdrop content-class="shadow" header-bg-variant="dark">
      <template v-slot:modal-title>
        <b-container class="project-title-modal">
          {{data.name}}<br>
          <b-badge variant="dark">{{data.desc}}</b-badge>
        </b-container>
      </template>

      <h3 v-html="data.about">{{data.about}}</h3>

      <b-button class="item-name" block @click="modalShow = false;">Close</b-button>
    </b-modal>

    <div class="project-title"><b-button v-b-modal.modal-1 class="project-link" @click="modalShow = !modalShow">{{data.name}}</b-button></div>
    <div class="project-image"><img :src="getPortfolioImg('gif')"></div>
  </div>
</template>

<script>
  import ProjectModal from './ProjectModal.vue'

  export default {    
    components: {
      ProjectModal
    },

    data() {
      return {
        modalShow: false
      }
    },

    props: {
      data: Object,
      default: {
        name: '',
        img:  '',
        youtube: '',
        github: '',
        desc: '',
        about: '',
      }
    },

    methods: {
      getPortfolioImg: function (type) {
        return require("../assets/" + this.data.img + '.' + type);
      },

      getPortfolioURL: function (projectURL) {
        window.location.href = projectURL;
      }
    }
  }
</script>

<style scoped>

  h3 {
    font-family: 'Rubik', sans-serif;
    text-align: left;
    color: #333333;
    font-size: 0.8vw;
    text-shadow: 2px 2px 4px #d5d5d5;
    font-weight: normal;
  }

  .project-title-modal {
    font-family: 'Exo', sans-serif;
    text-shadow: 2px 2px 4px #000000;
    color:#ffffff; 
    font-size: 1vw;
  }

  .project-link {
    font-family: 'Exo', sans-serif;
    text-shadow: 2px 2px 4px #000000;
    font-weight: bold;
    margin-top: 6vw;
    width: 15vw;
    border: none;
    border-radius: 15px;
    background:rgba(0,0,0,.7);
    font-size: 0.9vw;
    color:white;
  }

  .project-link:hover {
    background:#5cb85c;
    color:white;
    text-shadow: 2px 2px 4px #000000;
  }

  img {
    width: 100%;
    display: block;
  }

  h1 {
    color: #5cb85c;
    font-size: 2vw;
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

  .project {
    width: 17vw;
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
    .project-link {
      margin-top: 40vw;
      width: 80vw;
      border-radius: 15px;
      font-size: 4vw;
    }

    .project {
      width: 100%;
    }

    h1, h2, h3 {
      font-size: 9vw;
    }
  }
</style>