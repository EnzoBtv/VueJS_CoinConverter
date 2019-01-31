<template>
  <div id="app">
    <h2>Coin Converter</h2>
    <div class="linha">
      <Converter coin-a="USD" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="USD"></Converter>
    </div>
    <div class="linha">
      <Converter coin-a="CAD" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="CAD"></Converter>
    </div>
    <div class="linha">
      <Converter coin-a="EUR" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="EUR"></Converter>
    </div>
  </div>
</template>

<script>
import Converter from "./components/Converter.vue";

export default {
  name: "app",
  components: {
    Converter
  }
};
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.linha {
  display: flex;
  justify-content: space-between
}
</style>
