<template>
  <div class="container">
    <ul>
      <li v-for="post in posts" :key="post.id">
        <nuxt-link :to="`/posts/${post.slug}`">
          {{ post.title.rendered }}
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>

  export default {
    async asyncData({$axios}){
      return {
        posts: await $axios.$get('https://www.lasmesas.es/wp-json/wp/v2/posts')
    }
    }
  }
</script>
