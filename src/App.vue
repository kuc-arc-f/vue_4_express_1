<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <test1 />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import test1 from './components/test1.vue'

export default {
  name: 'app',
  components: {
    test1
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
