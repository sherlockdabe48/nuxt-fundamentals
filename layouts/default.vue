<template>
  <div class="container">
      <TheNavbar />
    <nuxt/>
  </div>
</template>


<script>
export default {
  components: {
    TheNavbar: ()=> import('~/components/TheNavbar.vue')
  }
}
</script>