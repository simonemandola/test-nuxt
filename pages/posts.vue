<template>
  <div>
    <h1>Post desde JSON placeholder</h1>
    <NuxtLink :to="{ name: 'index' }">Atrás</NuxtLink>
    <ul>
      <li v-for="(post, i) in posts" :key="i">
        <strong>{{ post.title }}</strong>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "posts",
  head() {
    return {
      title: "Página de posts | CCSTech.io",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Descripción de la página de post de CCSTech"
        }
      ],
      htmlAttrs: {
        lang: "es",
      }
    }
  },
  async asyncData({ $axios }) {
    const posts = await $axios.$get('https://jsonplaceholder.typicode.com/posts')
    return { posts }
  },
}
</script>

<style scoped>

  body {
    max-width: 60rem;
    margin: 0 auto;
  }

  ul {
    padding-left: 0;
  }

  li {
    padding: 1rem;
    border-bottom: 1px solid #cccccc;
  }

  li:hover {
    background-color: #f8f8f8;
  }

</style>
