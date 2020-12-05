<template>
  <div class="result">Delay: {{ reactionTime }}</div>
</template>

<script>
  export default {
    name: "Results",
    props: ['reactionTime']
  }
</script>

<style scoped>
  .result {
    width: 100px;
    padding: 20px;
    margin: 20px auto;
    border-radius: 10px;
    color: #ffffff;
    text-align: center;
    background: lightseagreen;
  }
</style>