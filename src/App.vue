<template>
  <div id="app">
    <ConversorTemperatura />
  </div>
</template>

<script>
import ConversorTemperatura from './components/ConversorTemperatura.vue'

export default {
  name: 'App',
  components: {
    ConversorTemperatura
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
#app {
  margin: 0;
  padding: 0;
  text-align: left;
  margin-top: 10px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}
</style>