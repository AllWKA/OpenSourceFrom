<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <username />
  </div>
</template>

<script>
import username from './components/form-username.vue'

export default {
  name: 'app',
  components: {
    username
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
