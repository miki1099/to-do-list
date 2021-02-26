<template>
  <project-header>To do list</project-header>
  <the-resources></the-resources>
</template>

<script>

import ProjectHeader from './components/header/ProjectHeader.vue'
import TheResources from './components/to-do-resources/TheResources.vue'

export default {
  components: { ProjectHeader, TheResources },
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
* {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
