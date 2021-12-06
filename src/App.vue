<template>
<h1>Test Your Reflex</h1>
<button @click="start" :disabled="isPlaying">Play</button> <br>
<Block v-if="isPlaying" :delay="delay" @end="endGame" />
<Result :score="reactionTime" v-if="showResult" />
</template>

<script>

import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Block,
    Result,
  },
  data() {
    return{
      isPlaying: false,
      delay: null,
      reactionTime: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.showResult = false
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    },

    endGame(reactionTime) {
      this.reactionTime = reactionTime
      this.showResult = true
      this.isPlaying = false
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
