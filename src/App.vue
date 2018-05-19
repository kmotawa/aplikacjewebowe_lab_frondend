<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <h4>Zaloguj sie e-mailem</h4>
    <div v-if="!isAuthenticated">
    <input type="email" v-model="email">
    <button @click="logIn()">Zaloguj</button>
     </div>
     <div v-else>
    Zalogowany jako {{email}}
    <button @click="logOut()">Wyloguj</button>
     </div>
    

   </div>



</template>

<script>
import "milligram"
import LoginForm from "./LoginForm";
export default {
  components: {LoginForm},
  data () {
    return {
      email: '',
      isAuthenticated: false
    }
  },
  methods: {
  logIn() {
    this.isAuthenticated = true;
  },
  logOut(){
    this.isAuthenticated = false;
  }
}
}
</script>

<style lang="scss">
</style>
