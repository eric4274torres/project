<template>
  <CalculatorApp/>
</template>

<script>
import CalculatorApp from './components/CalculatorApp.vue';

export default {
  name: 'App',
  components: {
    CalculatorApp
}
}
</script>

<style>
#app {
  width: 90vh;
  height: 45vh;
  font-family: 'Space Mono', monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
html{
    height: 100vh;
}
body{
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: hsl(185, 41%, 84%);
    background-image: url(../public/logo.svg);
    background-repeat: no-repeat;
    background-position: center 20%;
    font-family: 'Space Mono', monospace;
}
</style>
