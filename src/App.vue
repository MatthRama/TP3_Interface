<template>
  <div id="app">
    <base-layout>
      <HomePage />
    </base-layout>
  </div>
</template>

<script>
import BaseLayout from './components/BaseLayout.vue'
import HomePage from './components/HomePage.vue'

export default {
  name: 'App',
  components: {
    BaseLayout,
    HomePage
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
