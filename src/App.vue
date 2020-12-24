<template>
  <div>
    <div id="app">
      <NavBar />
    </div>
    <AppFooter />
  </div>
</template>

<script>
import NavBar from './components/NavBar';
import AppFooter from './components/AppFooter';

export default {
  name: 'App',
  components: {
    NavBar,
    AppFooter,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

@media (min-height: 723px) {
  #app {
    min-height: calc(100vw - 667px);
    background-color: white;
  }
}

@media (max-width: 1580px) {
  #app {
    min-height: calc(100vh - 30px);
    background-color: white;
  }
}
</style>
