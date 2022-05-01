<template>
  <div class="block" v-if="showBlock">
    <span>Click Me!</span>
  </div>
</template>

<script>
  export default {
    props: ['delayAmount'],

    data() {
      return {
        showBlock: false
      }
    },
  
    mounted() {
      setTimeout(() => {
        this.showBlock = true
      }, this.delayAmount)
    }
  }
</script>

<style>
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