<template>
  <Indecision />
  <!--<img alt="Vue logo" src="./assets/logo.png">-->
  <!--<Counter title="Beginning"/>-->
  <!--<Counter :start="100"/>-->
  <!-- if I write this :start="100" is like a number-->
</template>

<script>
import Counter from './components/Counter.vue'
import Indecision from './components/Indecision.vue'

export default {
  name: 'App',
  components: {
    Counter, Indecision
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
