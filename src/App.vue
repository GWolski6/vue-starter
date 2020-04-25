<template>
  <div>
      <h1>Witaj w systemie do zapisow na zajecia</h1>

      <div v-if="authenticatedUsername != ''">
          <h3> Jestes zalogowany jako: {{authenticatedUsername}} </h3>
          <button @click="logMeOut()">Wyloguj</button>
      </div>

      <div v-else>
        <input type="text" v-model="email">
        <button @click="logMeIn()">Zaloguj</button>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      authenticatedUsername: ''
    };
  },
  methods: {
    logMeIn() {
      this.authenticatedUsername = this.email;
      this.email ='';
    },

    logMeOut(){
      this.authenticatedUsername ='';
    }
  }
}

</script>

<style>
</style>
