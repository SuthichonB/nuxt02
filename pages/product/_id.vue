<template>
  <div style="text-align : center">
     <img width="400" :src="this.$route.params.id.image_url" alt="">
    <h1> {{ this.$route.params.id.title }}</h1>
    <div>{{ this.$route.params.id.synopsis }}</div>
    <a :href="this.$route.params.id.url" variant="primary">Go url</a>
  </div>
</template>
<script>
export default {
}
</script>
<style>
</style>