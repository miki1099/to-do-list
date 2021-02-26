<template>
    <base-card>
    <li>
        <div>
            <header>
                <h2>{{ resource.title }}</h2>
                <button>Delete</button>
            </header>
        </div>
        <p>{{resource.description}}</p>
        <a :href="resource.link">Link</a>
    </li>
</base-card>
</template>

<script>
export default {
    props: {
        resource: {
            id: String,
            title: String,
            description: String,
            link: String
        }
    }
}
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce0090;
}

a:hover,
a:active {
  color: #05004b;
}
</style>