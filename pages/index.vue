<template>
  <div>
    <Welcome />
    <router-link :to="{name: 'pagina'}">Página de posts</router-link>
  </div>
</template>

<script>
import Welcome from '@/components/Welcome'
export default {
  head() {
    return {
      title: "Página de inicio | CCSTech.io",
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
  name: 'index',
  components: {
    welcome: Welcome,
  },
}
</script>
