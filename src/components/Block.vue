<template>
  <div class="block" v-if="isVisible" @click="stopTimer">
    Click me as fast as you can!
  </div>
</template>

<script>
  export default {
    name: "Block",
    props: ['delay'],
    data() {
      return {
        isVisible: false,
        timer: null,
        reactionTime: 0
      }
    },
    methods: {
      startTimer() {
        this.timer = setInterval(() => this.reactionTime += 10, 10)
      },
      stopTimer() {
        console.log('stopTimer');
        clearInterval(this.timer);
        this.$emit('end', this.reactionTime)
      },
    },
    mounted() {
      setTimeout(() => {
        this.isVisible = true;
        this.startTimer();
      }, this.delay)
    },
  }
</script>

<style scoped>
  .block {
    width: 400px;
    border-radius: 20px;
    background: #bf8184;
    color: #ffffff;
    text-align: center;
    font-weight: bold;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>