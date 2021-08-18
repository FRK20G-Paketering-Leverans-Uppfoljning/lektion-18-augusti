<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Timer msg="Welcome to Your Vue.js App"/>
    <Countdown />
  </div>
</template>

<script>
import Timer from './components/Timer.vue';
import Countdown from './components/Countdown.vue';

export default {
  name: 'App',
  components: {
    Timer,
    Countdown
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
