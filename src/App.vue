<template>
  <div id="app">
    <h1>Witamy w systemie zapisów</h1>
      <div v-if="email.length > 0">
        <logged-in-page :email="email" 
                        @logout="logMeOut()">
        </logged-in-page>
      </div>
      <div v-else>
        <login-form @login="logMeIn($event)"
                    button-label = "Zaloguj"
                    header= "Zaloguj się z użyciem adresu mail">
        </login-form>                    
        <login-form @login="logMeIn($event)"
                    button-label = "Zarejestruj"
                    header= "Zarejestruj się z użyciem adresu mail">></login-form>
      </div>
  </div>

<!-- button-label = "2 + 2" wypisze "4 + 4"
                    :button-label = "2 + 2" wypisze "8". Dwukropek ewaluje wartość stringa na kod -->
</template>

<script>
  import "milligram";
  import LoginForm from "./LoginForm"
  import LoggedInPage from "./LoggedInPage"
  
  export default {
    components: {LoginForm, LoggedInPage},
    data(){
      return {
        email: ''
      };
    },
  methods:{
      logMeIn(username){
        this.email = username
      },
      logMeOut(){
        this.email = ''
      }
    }
  }

</script>

<style>


</style>
