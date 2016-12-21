<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello></hello>
    <pre style="text-align:left;font-size:10px">Vue.cordova: {{ cordova }}</pre>
  </div>
</template>

<script>
import Hello from './components/Hello'
import Vue from 'vue'

export default {
  name: 'app',
  components: {
    Hello
  },
  data: function () {
    return {
      cordova: Vue.cordova
    }
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
