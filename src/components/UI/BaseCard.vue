<template>
    <div id="card">
        <slot></slot>
    </div>
</template>

<style scoped>
#card {
  border-radius: 20px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.383);
  padding: 1rem;
  margin: 2rem auto;
  max-width: 40rem;
  background-color: rgb(233, 233, 233);
}
</style>