<template>
    <ul >
    <base-card>
        <to-do-resources v-for="res in resources" :key="res.id" :resource="res"></to-do-resources>
    </base-card>
    </ul>
</template>

<script>
import ToDoResources from './ToDoResources.vue'

export default {
    components: {
    ToDoResources
  },
  inject: ['resources']
  
}
</script>
<style scoped>
ul {
    margin: 0%;
    padding: 0%;
    margin: auto;
    max-width: 40rem;
    list-style: none;
}
</style>