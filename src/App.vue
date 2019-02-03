<template>
  <div id="app">
    <tquiz msg="Quiz-Quizan"/>
  </div>
</template>

<script>
import tquiz from './components/tquiz.vue'

export default {
  name: 'app',
  components: {
    tquiz
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
