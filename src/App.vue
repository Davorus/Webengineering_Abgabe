<template>
  <div class="app">
    <Navigation @clicked="listenToNav"/>
    <!--v-if for conditional rendering-->
    <div v-if="(this.page === 0)" class="homepage">
      <Home />
    </div>
    <div v-if="(this.page === 1)" class="Hersteller-Auswahl">
      <Hersteller />
    </div>
    <div v-if="(this.page === 2)" class="Kontakt">
      <Kontakt />
    </div>
    <div v-if="(this.page === 3)" class="Login">
      <Login />
    </div>
    <link 
      rel="stylesheet" 
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
      crossorigin="anonymous"
    >
  </div>
  <router-view />
</template>

<script>
//Imports so that the App can render them
import Navigation from './components/Navigation.vue';
import Home from './components/Home.vue';
import Kontakt from './components/Kontakt.vue';
import Hersteller from './components/Hersteller.vue';
import Login from './components/Login.vue';

export default {
  name: 'App',
  data() {
    return { //set values for variables 
      page: 0,
    }
  },
  components: { //Registration of components
    Navigation,
    Home,
    Kontakt,
    Hersteller,
    Login
  },
  methods: {
    //based on selected page there should be rendered the dedicated page
    listenToNav(selectedPage) {
      if(selectedPage === 0){ //Homepage
        this.page = 0;
      } else if (selectedPage === 1) { //Manufacturers
        this.page = 1;
      } else if (selectedPage === 2){ //Kontakt
        this.page = 2;
      } else { //Login
        this.page = 3;
      }
    }
  }
}
</script>

<style lang="scss"> //scss cause better than css

@import url("https://fonts.googleapis.com/css?family=Varela+Round");

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Varela Round", serif;
  font-weight: 400;
}

.app
{
  min-height: 100vh;
  position: relative;
  background-color: #F0F5F9; //Better than just a white background
}

.container {
  padding: 0 1em;
  max-width: 1140px;
  margin: 0 auto;
  padding-top: 4em;
  flex: auto;
  text-align: center;

    canvas {
      width: 100%;
      min-height: 250px;
      max-height: 500px;
    }
}

</style>
