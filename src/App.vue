<template>
  <h1>Reaction Timer</h1>
  <ScoreSheet />
  <button class="btn btn-primary" :disabled="isPlaying" @click="start">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="end_game"/>
  <br>
  <Results v-if="score" :score="score"/>
</template>

<script>
import Block from "./components/Block";
import Results from "./components/Results";
import ScoreSheet from "./components/ScoreSheet";

export default {
  name: 'App',
  components: {Block, Results, ScoreSheet},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      // console.log(this.delay)
      this.score = null
    },
    end_game(reaction_time) {
      this.score = reaction_time
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
  color: #444;
  margin-top: 60px;
}
</style>
