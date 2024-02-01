<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <!-- <p v-if="showResults">Reaction time: {{ score }} ms</p> -->
  <Results v-if="showResults" :score="score" />
</template>

<script>
  import Block from './components/Blocks.vue'
  import Results from './components/Results.vue'

 export default {
  name: 'App',
  components: { Block, Results },
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
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
    }
   }
 }
</script>


<style scoped>

</style>
