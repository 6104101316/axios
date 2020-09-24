<template>
  <div id="app">
    <b-container fluid class="bv-example-row mb-4">
      <img src="./assets/headphones.png" />
    </b-container>
    <br />
    <appmusic />
  </div>
</template>

<script>
import appmusic from "./components/appmusic.vue";
export default {
  name: "App",
  components: {
    appmusic,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  background-image: url(https://cdn.pixabay.com/photo/2017/10/25/03/40/musical-background-2886886_1280.jpg);
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: 100% 100%;
  height: 100vh;
}
/* body {background: bottom;} */
</style>
