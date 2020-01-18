<template>
  <div id="app">
    <Chmod />
    <Ls />
    <p>$ </p>
  </div>
</template>

<script>
import Chmod from './components/Chmod.vue'
import Ls from './components/Ls.vue'

export default {
  name: 'app',
  components: {
    Chmod,
    Ls
  }
}
</script>

<style>
#app {
  font-family: monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 18px;
}
</style>
