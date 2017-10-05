<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
import rem from '../static/rem.js'
export default {
  name: 'app',
  mounted () {
    rem.adapt(320, 100)
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background: #dedede;
}
</style>
