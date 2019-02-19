<template>
  <div id="app">
    <h4>Example Vuejs with Vue-apollo</h4>
    <pictures />
  </div>
</template>

<script>

import Pictures from './components/Pictures'

export default {
  name: 'app',
  components: {
    Pictures
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
