<template>
  <div id="app">
    <HelloWorld />

    <div>
      <h2>Respuestas</h2>
      <p>1: b </p>
      <p>2: b </p>
      <p>3: c </p>
      <p>4: b </p>
      <p>5: b</p>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
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
</style>
