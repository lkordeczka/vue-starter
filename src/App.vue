<template>
  <div id="app">
    <h1>ążźćół</h1>
    <p>{{ email }}</p> <!-- email jest zmienną szukaną w klasie -->
    <p>{{ password }}</p>
    <!-- v-mode pozwala dodać specjalny atrybut vue, v-model="email" pozwala edytować wartość email -->
    <table>
      <!-- <tr>
        <td>
          <p>mail: </p>
        </td>
        <td>
          <div v-if="email.length < 10">Ale masz krótki adres!</div>
          <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
          <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
          <input type="text" v-model="email"><button @click="alertMyEmail()"></button>
        </td>
      </tr>
      <tr>
        <td>
          <p>password: </p>
        </td>
        <td>
          <input type="text" v-model="password">
        </td>
      </tr> -->
      <tr>
        <td>
          <p>Add1: </p>
        </td>
        <td>
          <div v-if="isAuthencited">
            <div v-if="email.length == 0">Wpisz swój mail</div>
            <input type="text" v-model="email"><button @click="">Zaloguj się</button>
          </div>
          <div v-if="isAuthencited">
            <div v-else-if="email.length == 0">Wpisz swój mail</div>
            <input type="text" v-model="email"><button @click="">Zaloguj się</button>
          </div>          
        </td>
      </tr>        
    </table>
  
    <div v-if="isAuthencited">
      <p>Zaloguj jako</p>
      <button>
    </div>
    




  </div>
</template>

<script>
// Odpowiednik klasy odpowiadający za wygląd komponentu
export default {
// Odpowiednik metody nieprzyjmującej żadnego argumentu
  data(){
    return {
      email: 'jakisMail@o2.pl',
      password: 'jakies haslo'
    }
  }, //Musi byc przecinek(całe ciało klasy jest obiektem joson)
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(){
      this.isAuthencited = true;
    },
    logMeOut(){
      this.isAuthencited = false;
      this.email = '';
    }



  }
}


</script>

<style>


</style>
