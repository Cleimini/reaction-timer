<template>
  <p>Reaction Time is: {{ finalScore }}ms</p>
</template>

<script>
  export default {
    props: ['finalScore']
  }
</script>

<style scoped>
  p {
    font-style: italic;
  }
</style>