<template>
  <div>
  	<h1>Witaj w systemie do zapisow</h1>
    
    <div v-if="isAuntenthicated">
    	<h1>Witaj {{ email }}</h1>
    	<button @click="logMeOut">Wyloguj</button>
    </div>
    <div v-else>
    	<input type="text" v-model="email">
    	<button @click="logMeIn()">Zaloguj sie</button>
    	<div v-if="email.length < 10">Ale masz krótki adres!</div>
    	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    	<div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  data() {
	  return {
		  email: 'olakatosz@mail.com',
		  password: 'supersecretpassword',
		  isAuntenthicated: false
	  };
  },
    methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn() {
    	this.isAuntenthicated = true;
    },
    logMeOut() {
    	this.isAuntenthicated = false;
    	this.email = '';
    }
  }
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
