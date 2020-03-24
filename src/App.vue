<template>
  <div id="app">
    <Home :message="message" />
  </div>
</template>

<script>

import Home from './components/Home.vue';

export default {
  name: 'App',
  data(){
    return {
      message: "welcome to my app"
    }
  },
  components: {
    Home
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
