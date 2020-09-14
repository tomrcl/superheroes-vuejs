<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
    <SuperHeroes></SuperHeroes>
  </div>
</template>

<script>
import SuperHeroes from './components/SuperHeroes.vue'

export default {
  name: 'app',
  components: {
    SuperHeroes
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
