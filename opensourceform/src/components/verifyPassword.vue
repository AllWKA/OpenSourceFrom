<template>
  <div class="form-verifyPassword">
    <label for="vPassword">Verify your password: </label>
    <input type="password" v-model="passwd.spassword" id="vPassword">
  </div>
</template>

<script>
export default {
  name: 'verifyPassword',
  props:{
      passwd: {
        spassword: "",
      }
      
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
p{
    color: red;
}
</style>
