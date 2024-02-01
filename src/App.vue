<script>
  import Block from './components/Blocks.vue'

 export default {
  name: 'App',
  components: { Block },
   data() {
    return {
      isPlaying: false,
      delay: null
    }
   },
   methods: {
    start() { 
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    }
   }
 }
</script>

<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" :delay="delay"/>
</template>

<style scoped>

</style>
