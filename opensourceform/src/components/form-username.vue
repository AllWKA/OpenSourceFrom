<template>
    <div class="username">
      <label for="username">Username</label>
      <input type="text" v-model="username" placeholder="Username" v-on:keyup.enter="checkUsername()">
      <p>{{  error }}</p>
      
    </div>
</template>

<script>
export default {
  name: 'username',
  props: {
    // username: String
  },

  data: function() {
    return {

      username : '',
      error : '',
      letters: ['a','b','c'],
      words : [
        'thais',
        'david',
        'fran'
      ]
    }
  },

  methods : {
    checkUsername(){

      if (!this.checkLength()) {
        this.error = "El username es demasiado corto";
      }else{
        this.error = '';
      }
      if (!this.checkWords(this.words)) {
        this.error = "El Username no es válido";
      }
      
    },
    checkLength() {
      
      if (this.username.length <= 1 || this.username.length > 20) {
        return false;
      }else{
        return true;
      }
    },
    checkLetters(letters) {
      let arrayLettersUsername = this.username.split('');
      arrayLettersUsername.forEach(letritaUser => {
        letters.forEach(letrita =>{
          if (letritaUser == letrita) {
            return false;
          }
        })
      });
    },
    checkWords(words) {
      
      if (words.indexOf(this.username) == -1) {
        return true;
      }else{
        return false;
      }
    }
  }
}   
</script>


<style scoped>

input[type=text]:focus {
  border: 3px solid #555;
}

</style>
