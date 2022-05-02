<template>
  <p>Reaction Time is: {{ finalScore }}ms</p>
  <div class="rank">{{ rank }}</div>
</template>

<script>
  export default {
    props: ['finalScore'],

    data() {
      return {
        rank: null
      }
    },

    mounted() {
      if (this.finalScore < 250) {
        this.rank = 'Fast Reaction'
      } else if (this.finalScore < 400) {
        this.rank = 'Good Reaction'
      } else {
        this.rank = 'Slow Reaction'
      }
    }
  }
</script>

<style scoped>
  .rank {
    color: #0faf87;
    font-size: 1.4em;
    font-weight: bold;
  }
</style>