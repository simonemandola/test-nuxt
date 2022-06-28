<template>
  <div>
    <h1>Títulos de post desde JSON placeholder</h1>
    <router-link :to="{ name: 'index' }">Volver a la página de inicio...</router-link>
    <ul>
      <li v-for='(user, key) in data' :key='key'>
        <strong style='text-transform: capitalize'>{{ user.title }}</strong>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Página Simple | CCSTech.io",
      meta: [
        {
          hid: "description",
          name: 'description',
          content:"Sitio web de CCSTech.io"
        },
      ],
      htmlAttrs: {
        lang: "es",
      },
    };
  },
  name: 'pagina',
  data() {
    return {
      myData: {},
    }
  },
  computed: {
    data() {
      return this.myData;
    },
  },
  methods: {
    async getData() {
      const data = await fetch("https://jsonplaceholder.typicode.com/posts");
      this.myData = await data.json();
    },
  },
  async created() {
    this.getData();
  },
}
</script>

<style>
  body {
    font-family: Arial, sans-serif;
    max-width: 60rem;
    margin: 0 auto;
  }
  ul {
    padding-left: 0;
  }
  li {
    list-style: none;
    padding-block: .5rem;
    padding-inline: 1rem;
    border-bottom: 1px solid #cccccc;
  }
  li:hover {
    background-color: #f8f8f8;
  }
</style>
