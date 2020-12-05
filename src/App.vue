<template>
  <h1>Gezellig Reaction Timerrr!</h1>
  <button @click="play" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Results v-if="!isPlaying && reactionTime" :reactionTime="reactionTime"/>
</template>

<script>

  import Block from './components/Block';
  import Results from "./components/Results";

  export default {
    name: 'App',
    components: {
      Results,
      Block
    },
    data() {
      return {
        delay: null,
        isPlaying: false,
        reactionTime: 0
      }
    },
    methods: {
      play() {
        this.delay = 2000 + Math.random() * 3000;
        this.isPlaying = true;
      },
      endGame(reactionTime) {
        console.log('endGame reaction', this.reactionTime);

        this.isPlaying = false;
        this.reactionTime = reactionTime;
      }
    }
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
