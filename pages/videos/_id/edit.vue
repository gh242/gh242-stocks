<template>
  <div>
    <!-- <h1>Editing {{ $route.params.id }}</h1> -->
    <!-- {{video}} -->
    <h1>Editing {{ video.name }}</h1>
    <nuxt-link :to="`/videos/${video.id1}`">
      <button class="btn btn-primary">Go back to show</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: ['video'],
  head: {
    title: 'Edit'
  }
}
</script>

<style lang="scss" scoped>

</style>