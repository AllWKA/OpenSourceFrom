<template>
  <div class="form-password">
    <label for="password">Password: </label>
    <input type="password" v-model="password" id="password">
    <p v-if="valid == false"> La contraseña introducida no es válida. Debe contener mínimo: una minúscula, una mayúscula, un número y un carácter especial </p>
  </div>
</template>

<script>
export default {
  name: 'password',
  props:{
      password: "",
      valid: false
  },
  watch:{
      'password' (){
          if(this.password.match(/[a-z]+/g)&&this.password.match(/[A-Z]+/g)&&this.password.match(/\d/g)&&this.password.match(/\W+/g)&&this.password.length >= 8){
              this.valid = true;
          }
          return this.valid
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
