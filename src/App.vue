<template>
  <!-- <BingoVerano/>
  <CalculatorApp /> -->
  <AgendaTareas/>
</template>

<script>
// import CalculatorApp from "./components/CalculatorApp.vue";
// import BingoVerano from './components/BingoVerano.vue';
import AgendaTareas from "./components/AgendaTareas.vue";

export default {
  name: "App",
  components: {
    // CalculatorApp,
    // BingoVerano,
    AgendaTareas
  },
};
</script>

<style>
/* #app {
  width: 90vh;
  height: 45vh;
  font-family: "Space Mono", monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
} */
html {
  height: 100vh;
  font-size: 62.5%;
  box-sizing: border-box;
}
body {
  height: 100vh;
  display: flex;
  align-items: center;
  place-items: center;
  justify-content: center;
  /* background-color: hsl(185, 41%, 84%);
  background-image: url(../public/logo.svg);
  background-repeat: no-repeat;
  background-position: center 20%; */
  font-family: "Space Mono", monospace;
  margin: 0;
  min-width: 320px;
  min-height: 100vh;
  font-size: 1.6rem;
  background-color:#ececec;
}
</style>
