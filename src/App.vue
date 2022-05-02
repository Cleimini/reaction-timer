<template>
  <h1>Reaction Timer</h1>

  <button @click="startGame" :disabled="inSession">START GAME</button>

  <Block :delayAmount="delayAmount" @stop="stopGame" v-if="inSession" />

  <Result v-if="showResults" :finalScore="score" />
</template>

<script>
  import Block from './components/Block.vue'
  import Result from './components/Result.vue'

  export default {
    components: {
      Block,
      Result
    },

    name: 'App',

    methods: {
      stopGame(reactionTime) {
        this.inSession = false
        this.score = reactionTime
        this.showResults = true
      },

      startGame() {
        this.delayAmount = 2000 + Math.random() * 5000
        this.inSession = true
        this.showResults = false
      }
    },

    data() {
      return {
        delayAmount: null,
        inSession: false,
        score: null,
        showResults: false
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