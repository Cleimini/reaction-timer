<template>
  <div class="block">
    <span>Click Me!</span>
  </div>
</template>

<script>
  export default {
    props: ['delayAmount']
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