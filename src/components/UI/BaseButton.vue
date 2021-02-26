<template>
    <button :type="type" :class="mode">
        <slot></slot>
    </button>
</template>

<script>
export default {
    props: ['type', 'mode']
}
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #0093e9b6;
  border: 1px solid #3a006126;
  color: rgb(59, 59, 59);
  cursor: pointer;
  border-radius: 13px;
}

button:hover,
button:active {
  background-color: #ff0000b4;
  border-color: #270041;
}

.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
</style>