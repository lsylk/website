<template>
  <div id="app">
    <DrawerNavbar />
  </div>
</template>

<script>

import DrawerNavbar from "./components/DrawerNavbar";

export default {
  name: 'app',
  components: {
    DrawerNavbar
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
