<template>
  <div class="block" @click="stopTimer" v-if="showBlock">
    <span>Click Me!</span>
  </div>
</template>

<script>
  export default {
    methods: {
      startTimer() {
        this.timer = setInterval(() => {
          this.reactionTime += 10
        }, 10)
      },

      stopTimer() {
        clearInterval(this.timer)

        this.$emit('stop', this.reactionTime)
      }
    },

    props: ['delayAmount'],

    data() {
      return {
        reactionTime: 0,
        showBlock: false,
        timer: null
      }
    },
  
    mounted() {
      setTimeout(() => {
        this.showBlock = true
        this.startTimer()
      }, this.delayAmount)
    }
  }
</script>

<style scoped>
  .block {
    background: #0faf87;
    border-radius: 20px;
    color: white;
    cursor: pointer;
    font-size: 34px;
    font-weight: bolder;
    margin: 40px auto;
    padding: 100px 0;
    text-align: center;
    width: 400px;
  }
</style>