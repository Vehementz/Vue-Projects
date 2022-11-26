<template>
  <h1>Reaction timer</h1>
  <button @click="start">Play</button>
  <TimerBlock v-if="isPlaying" :delay="delay"/>
</template>

<script>

import TimerBlock from "./components/TimerBlock.vue";

export default {
  name: 'App',
  components: { TimerBlock},
  data() {
    return {
     isPlaying: false, 
     delay: null,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
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
  color: #7fb2e6;
  margin-top: 60px;
}
</style>