<template>
  <div class="form-email-container">
    <label>Email:</label>
    <input placeholder="placeHolder" type="email" />
  </div>
</template>

<script>
export default {
  name: "form-email",
  props: {
    msg: String
  },
  data(){
    return {
      disabled:{
        exist:false,
        value:""
      },
      max:{
        exist:false,
        value:""
      },
      step:{
        exist:false,
        value:""
      },
      name:{
        exist:false,
        value:""
      },
      value:{
        exist:false,
        value:""
      },
      email:{
        exist:false,
        value:""
      },
      placeHolder:{
        exist:false,
        value:""
      },
      maxlength:{
        exist:false,
        value:""
      },
      minlength:{
        exist:false,
        value:""
      },
      multiple:{
        exist:false,
        value:""
      },
      pattern: {
        exist:false,
        value:""
      },
      readonly:{
        exist:false,
        value:""
      },
      spellcheck:{
        exist:false,
        value:""
      }
    }
  },
  methods:{
    initializeSttributes() {
      
    },
    isDisable(){
      
    }
  },
  watch:{

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-email-container {
  display: flex;
  flex-flow: row;
}
.form-email-container label {
  flex-basis: 25%;
}
.form-email-container input {
  flex-basis: 75%;
}
</style>
