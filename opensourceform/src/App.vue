<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/welcome.jpg" />
    <HelloWorld />
    <password />
    <fromEmail :config="inputConfig1" />
    <fromEmail :config="inputConfig2" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import password from "./components/password.vue";
import fromEmail from "./components/From-Email.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    password,
    fromEmail
  },
  data() {
    return {
      inputConfig1: {
        mode: "login-username",
        value: "pruebitaNomas"
      },
      inputConfig2: {
        mode: "login-pwd"
      }
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
