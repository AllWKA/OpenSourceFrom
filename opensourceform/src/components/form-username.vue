<template>
    <div class="username">
      <label for="username">Username</label>
      <input type="text" v-model="username" placeholder="Username">
      <p>{{  username.split('').includes('a')   }}</p>
    </div>
</template>

<script>
export default {
  name: 'username',
  props: {
    username: String
  },

  methods : {

    checkUsername() {
      
    },
    checkLength() {
      if (this.username.length <= 1 || this.username.length >= 50) {
        return false;
      }
    },
    checkLetters(letters) {
      arrayLettersUsername = this.username.split('');
      arrayLettersUsername.forEach(letritaUser => {
        letters.forEach(letrita =>{
          if (letritaUser == letrita) {
            return false;
          }else{
            return true;
          }
        })
      });

    },
    checkWords(words) {
      
    }


  }
}


</script>


<style scoped>

input[type=text]:focus {
  border: 3px solid #555;
}

</style>
