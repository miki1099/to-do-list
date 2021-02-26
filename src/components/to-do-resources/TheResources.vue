<template>
    <base-card id="card">
        <base-button @click="setSelectedComponent('to-do-storage')" :mode="storageButtonMode">Stored resources</base-button>
        <base-button @click="setSelectedComponent('add-to-do-resource')" :mode="addButtonMode">Add Resource</base-button>
    </base-card>
    <keep-alive>
        <component :is="selectedComponent"></component>
    </keep-alive>
</template>

<script>
import ToDoStorage from './ToDoStorage.vue'
import AddToDoResource from './AddToDoResource.vue'

export default {
    components: {
        ToDoStorage,
        AddToDoResource
    },
    data(){
        return {
            selectedComponent: 'to-do-storage',
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
    },
    methods: {
        setSelectedComponent(tab) {
            this.selectedComponent = tab;
        },
        addResource(resource) {
            this.storedResources.push({
                id: resource.id, 
                title: resource.title,
                description: resource.description,
                link: resource.link
            });
        },
        removeResource(id){
            this.storedResources.pop(this.storedResources.filter(res => res.id === id));
        }
    },
    provide(){
        return {
            resources: this.storedResources,
            addResource: this.addResource,
            removeResource: this.removeResource
        }
    },
    computed: {
        storageButtonMode() {
            return this.selectedComponent === 'to-do-storage' ? null : 'flat';
        },
        addButtonMode(){
            return this.selectedComponent === 'add-to-do-resource' ? null : 'flat';
        }
    }
}
</script>

<style scoped>
    #card {
        display: flex;
        justify-content: space-around;
    }
</style>