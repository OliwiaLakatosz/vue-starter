<template>
  <div>
  	<h1>Witaj w systemie do zapisow</h1>
    
    <div v-if="email.length > 0">
    	<h1>Witaj {{ email }}</h1>
    	<button @click="logMeOut">Wyloguj</button>
    </div>
    
    <div v-else>
    	<!-- uzycie komponentu LoginForm, trzeba dodac drugi argument logforma - $event -->
    	<!-- jakbym chciala label czy header byl ewaluowany jako js to daje :header="2+2" i da mi 4 -->
	    <login-form @login="logMeIn($event)" :button-label="'Lece'" :header="2 + 2"></login-form>
	    <login-form @login="logMeIn($event)" :button-label="'Wlec'" header="2 + 2"></login-form>
		<login-form @login="logMeIn($event)" :button-label="'Zaloguj sie jak czlowiek'" header="Zaloguj sie"></login-form>
	    
    </div>
    
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./components/LoginForm.vue";

export default {
  components: { LoginForm },
  data() {
	  return {
		  email: '',
		  password: 'supersecretpassword',
	  };
  },
    methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(username) {
    	this.email = username;
    },
    logMeOut() {
    	this.email = '';
    }
  },
  
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
