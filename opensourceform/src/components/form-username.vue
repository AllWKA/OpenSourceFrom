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
      this.checkWords(this.words);
      if (this.username.length <= 1 || this.username.length > 20) {
        this.error = "El username es demasiado corto";
        return;
      }
    },
    checkLetters(letters) {
      let arrayLettersUsername = this.username.split('');
      arrayLettersUsername.forEach(letritaUser => {
        letters.forEach(letrita =>{
          if (letritaUser == letrita) {
            this.error = "El Username tiene una letra no valida";
            return;
          }
        })
      });
    },
    checkWords(words) {
      
      if (words.indexOf(this.username) == -1) {
        this.error='';
        this.error = "El UsernamePalabreja es válido";
      }else{
        this.error = "El Username no es válido";
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
