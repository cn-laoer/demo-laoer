<template>
  <div id="app">
    <vHome></vHome>
  </div>
</template>

<script>
import vHome from './components/home.vue';

export default {
  name: 'app',
  components: {
    vHome
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
