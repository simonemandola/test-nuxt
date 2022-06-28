<template>
  <div>
    <h1>Inicio</h1>
    <router-link :to="{ name: 'posts' }">Ver posts</router-link>
  </div>
</template>

<script>
export default {
  name: 'index'
}
</script>
