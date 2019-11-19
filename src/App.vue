<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <tasks></tasks> -->
    <markdown></markdown>
  </div>
</template>

<script>
// import Tasks from './components/Tasks'
import Markdown from './components/Markdown'

export default {
  name: 'App',
  components: {
    // Tasks
    Markdown
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
