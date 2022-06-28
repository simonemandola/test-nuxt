<template>
  <div>
    <h1>Post desde JSON placeholder</h1>
    <router-link :to="{ name: 'index' }">Atrás</router-link>
    <ul>
      <li v-for="(post, i) in allPost" :key="i">
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
  data() {
    return {
      myPosts: {},
    }
  },
  computed: {
    allPost() {
      return this.myPosts;
    }
  },
  methods: {
    async getPost() {
      const data = await fetch("https://jsonplaceholder.typicode.com/posts");
      this.myPosts = await data.json();
    }
  },
  mounted() {
    this.getPost();
  }
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
