<template>
  <h1>Reaction timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>

  <TimerBlock v-if="isPlaying" :delay="delay" @end="endGame"/>
  
  <TimerResults v-if="showResults" :score="score" />

  
  
</template>

<script>

import TimerResults from "./components/TimerResults.vue";
import TimerBlock from "./components/TimerBlock.vue";

export default {
  name: 'App',
  components: { TimerBlock, TimerResults},
  data() {
    return {
     isPlaying: false, 
     delay: null,
     score: null,
     showResults: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
      this.showResults = false;
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #7fb2e6;
  margin-top: 60px;
}

button {
  background-color: rgb(42, 42, 253);
  color: white;
  padding: 0.7rem 1rem;
  border-radius: 4px;
  cursor: pointer;
  letter-spacing: 2px;
  font-size: 16px;
}

button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}

</style>