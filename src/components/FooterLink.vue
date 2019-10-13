<template>
  <a :href="data.href" :target="data.target" rel="noopener" v-bind:class="{ 'vert-align': data.isIcon }">
    <span v-html="data.name">{{data.name}}</span>
    <span class="underline"></span>
  </a>
</template>

<script>
  export default {
    props: {
      data: Object,
      default: {
        name: '',
        href: '',
        target: ''
      }
    }
  }
</script>

<style scoped>
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

  .vert-align {
    vertical-align: sub;
  }

  .underline {
    position: absolute;
    width: 0;
    height: 4px;
    background: #ea495f;
    right: 0;
    top: 1.5vw;
    transition: all 0.2s ease;
    margin-left: -2px;
  }

  a:hover .underline {
    width: 100%;
    left: 2px;
  }

  @media (max-width: 1200px)
  {
    a {
      font-size: 15px;
    }

    .underline {
      top: 20px;
    }
  }
</style>