<template>
  <div class="my-app">
<!--    <h1>Twój email to {{email}}</h1>-->
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="loggedIn == false">
        <p>Zaloguj się e-mailem
        <input type="email" v-model="email">
        <button @click="login()">Wchodzę</button></p></div>
    <div v-if="loggedIn == true">
        <p>Witaj {{email}}</p>
        <p id="p2" @click="logout()">Wyloguj</p></div>
    </div>


<!--    <div v-if="email.length < 10">Ale masz krótki adres!</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>-->
<!--    <div v-if="!email.includes('@')" > To nie jest adres email! </div>-->
<!--    {{email.length}}-->

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
export default {
  data() {
    return {
      email: '',
      password: '',
      loggedIn: false,
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    login(){
      this.loggedIn = true;
    },
    logout(){
      this.loggedIn = false;
      this.email = '';
    }
  },
  components: {LoginForm},

}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: left;
  color: #2c3e50;
}

#p2 {
  color : dodgerblue;
}

</style>
