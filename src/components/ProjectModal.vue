<template>
  <div>
    <transition name="modal">
      <div v-if="isOpen">
        <div class="overlay" @click.self="isOpen = false;">
          <div class="modal">
            <h1>{{data.name}}</h1>
            <h2>{{data.desc}}</h2>
            <h3 v-html="data.about">{{data.about}}</h3>
            <button v-if="data.youtube != ''" class="button" v-on:click="getPortfolioURL(data.youtube)">
             View on YouTube
            </button>
            <button v-if="data.website != ''" class="button" v-on:click="getPortfolioURL(data.website)">
             View on the Web
            </button>
            <button v-if="data.github != ''" class="button" v-on:click="getPortfolioURL(data.github)">
             View on GitHub
            </button>
          </div>
        </div>
      </div>
    </transition>
    <img v-bind:src="getPortfolioImg('gif')" @click="isOpen = !isOpen;">
  </div>
</template>

<script>
  export default {
    data: function ()
    {
      return {
        isOpen: false,
        portfolio: []
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

    props: {
      data: Object
    }
  }
</script>

<style scoped>

  .button {
    font-family: 'Rubik', sans-serif;
    font-size: 1vw;
    background: none;
    border: none;
    color: #428bca;
    padding: 1vw;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    margin-top: 2.5vw;
    margin-left: 1vw;
    padding: 0.5vw;
    cursor: pointer;
    -webkit-transition-duration: 0.4s;
    transition-duration: 0.4s;
    border-radius: 15px;
    border: 2px solid #428bca;
  }

  .button:hover {
    box-shadow: 0 5px 10px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
    opacity: 1;
    background-color: #428bca;
    color: #ffffff;
  }

  img {
    width: 100%;
    display: block;
  }

  h1 {
    font-family: 'Ubuntu', sans-serif;
    text-align: left; 
    color: #449d44;
    margin-top: 2.5vw;
    margin-left: 1vw;
    font-size: 1.5vw;
    text-shadow: 2px 2px 4px #d5d5d5;
  }

  h2 {
    font-family: 'Ubuntu', sans-serif;
    text-align: left;
    color: #228888;
    margin-top: 1vw;
    margin-left: 1vw;
    font-size: 1vw;
    text-shadow: 2px 2px 4px #d5d5d5;
  }

  h3 {
    font-family: 'Rubik', sans-serif;
    text-align: left;
    color: #333333;
    margin-top: 1vw;
    margin-left: 1vw;
    font-size: 0.8vw;
    text-shadow: 2px 2px 4px #d5d5d5;
    font-weight: normal;
  }

  .modal {
    width: 50vw;
    margin: 0px auto;
    padding: 1vw;
    background-color: #e5e7e7;
    border-radius: 2px;
    box-shadow: 0 5px 10px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
    transition: all 0.2s ease-in;
    font-family: Helvetica, Arial, sans-serif;
    opacity: 0.95;
    border-radius: 15px;
  }
  .fadeIn-enter {
    opacity: 0;
  }

  .fadeIn-leave-active {
    opacity: 0;
    transition: all 0.2s step-end;
  }

  .fadeIn-enter .modal,
  .fadeIn-leave-active.modal {
    transform: scale(1.1);
  }

  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background: #00000094;
    z-index: 999;
    transition: opacity 0.2s ease;
  }

  @media (max-width: 1400px) {

    h1, h2, h3 {
      font-size: 11px;
    }

    .modal {
      width: 95%;
    }

    .button {
      font-size: 14px;
    }
    
  }
</style>