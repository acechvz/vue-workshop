<template>
  <div id="app">
    <PlayGround />
  </div>
</template>

<script>
import PlayGround from './components/PlayGround'

export default {
  name: 'App',
  components: {
    PlayGround
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
