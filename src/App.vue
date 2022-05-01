<template>
  <h1>Reaction Timer</h1>

  <button @click="startGame" :disabled="inSession">START GAME</button>

  <Block 
    v-if="inSession"
    
    :delayAmount="delayAmount"
  />
</template>

<script>
  import Block from './components/Block.vue'

  export default {
    components: {
      Block
    },

    data() {
      return {
        delayAmount: null,
        inSession: false
      }
    },

    name: 'App',

    methods: {
      startGame() {
        this.delayAmount = 2000 + Math.random() * 5000,
        this.inSession = true
      }
    }
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