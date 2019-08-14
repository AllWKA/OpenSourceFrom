<template>
  <div class="form-nombre-y-apellidos" >
    <input type="text" placeholder="nombre" v-model="nombre">
    <p> {{}} </p>
    <input type="text" placeholder="apellidos" v-model="apellido">
    <p> </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    nombre: "",
    apellido: ""
  },
  watch: {
    validacion(){
       if (typeof nombre != "string") {
         
    }
  }
}    

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
