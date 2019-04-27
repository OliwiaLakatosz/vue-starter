<template>
  <div>
  	<h1>Witaj w systemie do zapisów</h1>
    
    <div v-if="email.length > 0">
    	<logged-in-page :username="email" @logout="logMeOut()"></logged-in-page>
    </div>
    
    <div v-else>
	    <login-form @login="logMeIn($event)" :button-label="'Zaloguj się'" header="Logowanie"></login-form>
    </div>
    
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./components/LoginForm.vue";
import LoggedInPage from "./components/LoggedInPage.vue";

export default {
  components: { LoginForm, LoggedInPage },
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
