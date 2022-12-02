<template>
  <div class="app">
    <Navigation />
    <router-view />
    <Home />
    <link 
      rel="stylesheet" 
      href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
      integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
      crossorigin="anonymous"
    >
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue';
import Home from './components/Home.vue';

export default {
  name: 'App',
  components: {
    Navigation,
    Home,
  }
}
</script>

<style lang="scss">

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
  background-color: #F0F5F9;
}

.container {
  padding: 0 20px;
  max-width: 1140px;
  margin: 0 auto;
  padding-top: 4em;
}

</style>
