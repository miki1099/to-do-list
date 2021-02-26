<template>
<project-header>To do list</project-header>
  <div>
      <to-do-storage :resources="storedResources"></to-do-storage>
  </div>
</template>

<script>
import ToDoStorage from './components/to-do-resources/ToDoStorage.vue'
import ProjectHeader from './components/header/ProjectHeader.vue'

export default {
  components: { ToDoStorage, ProjectHeader },
  data() {
    return {
      storedResources: [
        { id: 'google', 
        title: 'Google', 
        description: 'Learn using google',
        link: 'https://www.google.com/'
        },
        { id: 'Vue', 
        title: 'Vue', 
        description: 'Learn vue basics',
        link: 'https://cli.vuejs.org/'
        }
      ]
    };
  }
  
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
