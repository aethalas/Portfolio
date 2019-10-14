<template>

  <div class="project">
    <b-modal v-model="modalShow" id="modal-1" size="xl" hide-footer hide-header-close no-close-on-esc no-close-on-backdrop content-class="shadow" header-bg-variant="dark">
      <template v-slot:modal-title>
        <b-container class="project-title-modal">
          {{data.name}}<br>
          <b-badge variant="dark">{{data.desc}}</b-badge>
        </b-container>
      </template>

      <b-container>

        <b-row v-if="data.youtube != ''">
          
          <b-col class="portfolio-youtube">
            <b-container>
              <div>
                <b-embed
                  type="iframe"
                  aspect="16by9"
                  :src="data.youtube"
                  allowfullscreen
                ></b-embed>
              </div>
            </b-container>
          </b-col>
        </b-row>

        <b-row >
          <b-col class="portfolio-buttons">
            <b-container >
                
              <b-button v-if="data.youtube != ''" class="button" style='margin-right:5px;' v-on:click="getPortfolioURL(data.youtube)">
              View on YouTube
              </b-button>
              <b-button v-if="data.website != ''" class="button" style='margin-right:5px;' v-on:click="getPortfolioURL(data.website)">
              View on the Web
              </b-button>
              <b-button v-if="data.github != ''" class="button" v-on:click="getPortfolioURL(data.github)">
              View on GitHub
              </b-button>

            </b-container>
          </b-col>
        </b-row>

        <b-row>
          <b-col class="portfolio-information">
            <b-container>
              <h3 v-html="data.about">{{data.about}}</h3>
            </b-container>
          </b-col>
        </b-row>
      </b-container>

      <b-button class="portfolio-button" block @click="modalShow = false;">Close</b-button>
    </b-modal>

    <div class="project-title"><b-button v-b-modal.modal-1 class="project-link" @click="modalShow = !modalShow">{{data.name}}</b-button></div>
    <div class="project-image"><img :src="getPortfolioImg('gif')"></div>
  </div>
</template>

<script>
  export default {    
    components: {

    },

    data() {
      return {
        modalShow: false
      }
    },

    props: {
      data: Object,
      default: {
        percent: '',
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
  .button {
    font-family: 'Exo', sans-serif;
    text-shadow: 2px 2px 4px #e6e6e6;
    font-weight: bold;
    vertical-align: bottom; 
    border: none;
    border-radius: 15px;
    background: rgba(255, 255, 255,0);
    font-size: 0.9vw;
    color:#505a55; 
    margin-top: 10px;
  }

  .button:hover {
    background:#505a55;
    color:white;
    text-shadow: 2px 2px 4px #000000;
  }

  .portfolio-button {
    font-family: 'Exo', sans-serif;
    text-shadow: 2px 2px 4px #e6e6e6;
    font-weight: bold;
    vertical-align: bottom; 
    width: 100%;
    border: none;
    border-radius: 15px;
    background: rgba(255, 255, 255,0);
    font-size: 0.9vw;
    color:#505a55; 
    margin-top: 10px;
  }

  .portfolio-button:hover {
    background:#505a55;
    color:white;
    text-shadow: 2px 2px 4px #000000;
  }

  .portfolio-youtube {
    font-family: 'Ubuntu', sans-serif;
    border-radius: 15px;
    background: #dfdfdf;
    padding: 1vw; 
    width: 100%;
    font-size: 20px;
    margin: 5px;
    text-shadow: 2px 2px 4px #d5d5d5;
    background: repeating-linear-gradient(
      120deg,
      #ffffff,
      #ffffff 10px,
      #d4e9dd 10px,
      #d4e9dd 20px
    );
  }

  .portfolio-buttons {
    font-family: 'Exo', sans-serif;
    border-radius: 15px;
    background: #dfdfdf;
    padding: 1vw; 
    display: inline-block;
    position: relative;
    text-align: center;
    width: 100%;
    font-size: 20px;
    margin: 5px;
    text-shadow: 2px 2px 4px #d5d5d5;
    background: repeating-linear-gradient(
      120deg,
      #ffffff,
      #ffffff 10px,
      #f8f9ff 10px,
      #f8f9ff 20px
    );
  }

  .portfolio-information {
    font-family: 'Ubuntu', sans-serif;
    border-radius: 15px;
    background: #dfdfdf;
    padding: 1vw; 
    width: 100%;
    font-size: 20px;
    margin: 5px;
    text-shadow: 2px 2px 4px #d5d5d5;
    background: repeating-linear-gradient(
      120deg,
      #ffffff,
      #ffffff 10px,
      #f5f5f5 10px,
      #f5f5f5 20px
    );
  }

  h3 {
    font-family: 'Exo', sans-serif;
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
    .project-title-modal {
      font-size: 20px;
    }

    .button {
      font-size: 20px;
    }

    .portfolio-button {
      font-size: 20px;
    }

    .project-link {
      margin-top: 35vw;
      width: 80vw;
      border-radius: 15px;
      font-size: 20px;
    }

    .project {
      width: 95%;
    }

    h1, h2, h3 {
      font-size: 20px;
    }
  }
</style>