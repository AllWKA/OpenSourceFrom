<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/welcome.jpg">
    <HelloWorld />
    <password/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import password from './components/password.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    password
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
