<template>
  <div @keyup.enter="verifyPassword()" class="form-password">
    <label for="password">Password: </label>
    <input  type="password" v-model="password" id="password">
    <vPassword :passwd='vpassword'/>
    <p v-if="notValid"> La contraseña introducida no es válida. Debe contener mínimo: una minúscula, una mayúscula, un número y un carácter especial </p>
    <p v-if="notVerified"> Las contraseñas introducidas no son iguales</p>
  </div>
</template>

<script>

import vPassword from './verifyPassword.vue'

export default {
  name: 'password',
  data(){
    return{
      password: "",
      notValid: false,
      vpassword:{
        spassword:"",

      },
      notVerified: false
    }
      
  },
  components:{
      vPassword
  },
  watch:{
      'password' (){
        
          if(this.password.match(/[a-z]+/g)&&this.password.match(/[A-Z]+/g)&&this.password.match(/\d/g)&&this.password.match(/\W+/g)&&this.password.length >= 8){
              this.notValid = false;
          }else{
            this.notValid = true;
          }
          return this.notValid
      }
  },
  methods:{
    verifyPassword() {
      console.log(this.password);
      console.log(this.vpassword.spassword);
      if(this.password == this.vpassword.spassword){
        this.notVerified = false;
      }else{
        this.notVerified = true
      }

      return this.notVerified;
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
