<template>
<base-card>
    <form @submit.prevent="submitData" >
        <div class="form-block">
            <label for="title">Title</label>
            <input type="text" placeholder="title" name="title" v-model="resource.title"/>
        </div>
        <div class="form-block">
            <label for="description">Description</label>
            <textarea placeholder="description" name="description" rows="3" v-model="resource.description"/>
        </div>
        <div class="form-block">
            <label for="link">Link</label>
            <input type="url" placeholder="link" name="link" v-model="resource.link"/>
        </div>
        <br>
        <base-button type="submit">Add to list</base-button>
    </form>
</base-card>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue';
export default {
  components: { BaseButton },
    inject: ['addResource'],
    data() {
        return {
            resource: { 
                id: '', 
                title: '', 
                description: '',
                link: ''
            },
        };
    },
    methods: {
        submitData() {
            this.resource.id = new Date().toISOString;
            this.addResource(this.resource);
            this.resource.id = '';
            this.resource.title = '';
            this.resource.description = '';
            this.resource.link = '';
        }
    }
}
</script>

<style scoped>

label {
  font-weight: bold;
  display: block;
  margin-top: 1.5rem;
}

input,
textarea {
  display: block;
  margin-left: -50%;
  width: 200%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #e2ffe3;
}

* {
    text-align: center;
}
.form-block {
  margin: 1rem 0;
}
</style>