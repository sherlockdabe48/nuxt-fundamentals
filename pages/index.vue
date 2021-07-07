<template>
  <section class="container">
    <div>
      <NuxtLogo/>
      <h1 class="title">
        nuxt-fundamentals
      </h1>
    
      <h2 class="subtitle">
        My gnarly Nuxt.js project
      </h2>
      <NLink
      v-for="post in posts"
      :key="post.id"
      :to="{name: 'posts-id', params: {id: post.id}}"
      class="button--grey"
      >
      {{post.title}}
      </NLink>
    </div>
  </section>
</template>

<script>
export default {
  components: {
    NuxtLogo: () => import('~/components/NuxtLogo.vue')
  },
  head() {
    return {
      title: "Home Page",
      meta: [
        {name: 'twitter: title', content: 'Nuxt Fundamentals by Vue School'},
        {name: 'twitter: desciption', content: 'Nuxt + Vue = 🎉'},
        {name: 'twitter: image', content: 'https://lh3.googleusercontent.com/4afAeivL59duXDj3vOphH8t9HY0jnxTtEUO3jnjvCjQh0ox33JrbBg4H-SpfPa81cWgZUUMbeMjgwymfcuPVWfEcjuIJqGmkd8yna1-w6lY6fWOniRpoqTDczD3rVOqJng80Ig1Msw=w2400'},
        {name: 'twitter: card', content: 'summary_large_image'},
      ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
  'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}
.links {
  padding-top: 15px;
}
</style>