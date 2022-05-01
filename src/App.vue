<template>
  <h1>Reaction Timer</h1>

  <button @click="startGame" :disabled="inSession">START GAME</button>

  <Block :delayAmount="delayAmount" v-if="inSession" />
</template>

<script>
  import Block from './components/Block.vue'

  export default {
    components: {
      Block
    },

    name: 'App',

    methods: {
      startGame() {
        this.delayAmount = 2000 + Math.random() * 5000,
        this.inSession = true
      }
    },

    data() {
      return {
        delayAmount: null,
        inSession: false
      }
    },
  }
</script>

<style>
  #app {
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    color: #444;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    margin-top: 60px;
    text-align: center;
  }
</style>