<template>
  <div>
      <h1>Witaj w systemie do zapisow na zajecia</h1>

      <div v-if="authenticatedUsername != ''">
          <h3> Jestes zalogowany jako: {{authenticatedUsername}} </h3>
          <button @click="logMeOut()">Wyloguj</button>
      </div>

      <div v-else>
        <login-form @login="logMeIn($event)" button-label="WejdŸ"></login-form>
        <login-form @login="logMeIn($event)" button-label="Wleæ"></login-form>
        <login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
      </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},
  data() {
    return {
      authenticatedUsername: ''
    };
  },
  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },

    logMeOut(){
      this.authenticatedUsername ='';
    }
  }
}

</script>

<style>
</style>
