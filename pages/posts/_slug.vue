<template>
  <div class="container">
    <nuxt-link :to="`/`">
      Home
    </nuxt-link>
    <h1 v-html="post.title.rendered"></h1>
    <br>
    <br>
    <p v-html="post.content.rendered"></p>
  </div>
</template>

<script>

  export default {
    async asyncData({$axios, params, payload}){
      if (payload) return { post:payload };
      const data = await $axios.$get('https://www.lasmesas.es/wp-json/wp/v2/posts?slug='+params.slug);
      return {
        post: data[0],
      }
    }
  }
</script>
