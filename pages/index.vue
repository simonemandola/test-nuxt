<template>
  <div>
    <h1>Inicio</h1>
    <NuxtLink :to="{ name: 'posts' }">Ver posts</NuxtLink>
  </div>
</template>

<script>
export default {
  name: 'index'
}
</script>
