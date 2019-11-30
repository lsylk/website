<template>
  <div id="app">
    <DrawerNavbar />
    <AppFooter />
  </div>
</template>

<script>
import DrawerNavbar from './components/DrawerNavbar';
import AppFooter from './components/AppFooter';

export default {
  name: 'App',
  components: {
    DrawerNavbar,
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
</style>
