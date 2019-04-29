<template>
  <div id="app">
    <img alt="Game of Thrones gif" src="./assets/success-logo.gif" />
    <HelloGot />
  </div>
</template>

<script>
import HelloGot from "./components/HelloGot.vue";

export default {
  name: "app",
  components: {
    HelloGot
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  background-color: black;
}
</style>
