<template>
  <div class="form-nombre-y-apellidos" >
    <input type="text" placeholder="nombre" v-model="user.nombre">
    <p v-if="user.invalid === true"> nombre inválido </p>
    <input type="text" placeholder="apellido" v-model="user.apellido">
    <p v-if="user.invalid2 === true"> Apellido inválido </p>
  </div>
</template>

<script>
export default {
  name: 'nombreYApellidos',
  props: {
    user:{
      nombre: String,
      apellido: String,
      invalid: Boolean,
      invalid2: Boolean
    }
    
  },
  watch: {
    "user.nombre" () {
       if ( typeof this.user.nombre != "string" || this.user.nombre === "" ) {
         return this.user.invalid = true
        } else{
          return this.user.invalid = false
        }
      },
    "user.apellido" () {
       if ( typeof this.user.apellido != "string" || this.user.apellido === "" ) {
         return this.user.invalid2 = true
        } else{
          return this.user.invalid2 = false
        }
    }
  }

}
</script>

//<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
