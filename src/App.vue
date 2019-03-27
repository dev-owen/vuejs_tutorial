<template>
  <div id="app">
    <navbar />
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="I love Prography"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import navbar from './components/navbar';
export default {
  name: 'app',
  components: {
    navbar,
    HelloWorld,
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
}

body { 
  margin: 0;
}
</style>
