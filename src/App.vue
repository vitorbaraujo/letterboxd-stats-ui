<template>
  <div id="app">
    <Header :user="user" />
    <MainStats :user="user" />
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import MainStats from './components/MainStats.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Header,
    MainStats
  },
  data: function() {
    return {
      user: {
        name: 'vitorbarbosa',
        gravatarUrl: '72c289424e0c1219de83996c0199cd5c'
      },
    }
  }
}
</script>

<style>
body {
  margin: 0px;
  background: #161b21;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1, h2, p {
    color: #9ab;
}
</style>
