<template>
  <div id="app">
    <router-view />
    <!-- <vHome></vHome> -->
  </div>
</template>

<script>
// import vHome from './components/home.vue';

export default {
  name: 'app',
  components: {
    // vHome
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
.has-gutter tr {
  width: 100%!important;
  height: 36px!important;
  background: #0f64b7;
  width: 100%;
  height: 30px;
  border-left: 2px solid #01cfff!important;
  border-right: 2px solid #01cfff;
}
.has-gutter tr td {
  font-size: 12px;
  font-weight: bold;
  color: #30bcec;
  text-align: center;
}
</style>
