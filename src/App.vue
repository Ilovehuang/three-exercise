<template>
  <div id="app">
    <Three4></Three4>
  </div>
</template>

<script>
import Scene from './components/Scene.vue'
import DrawingLine from './components/DrawingLine.vue'
import Three1 from './components/Three1.vue'
import Three2 from './components/Three2.vue'
import Three4 from './components/Three4.vue'
export default {
  name: 'app',
  components: {
    Three4
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
