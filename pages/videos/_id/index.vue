<template>
  <div>
    <!-- We're are in video {{ $route.params.id }} -->
    <h2>We're are in video {{ video.name }}.</h2>
    <nuxt-link :to="`/videos/${video.id1}/edit`">
      <button class="btn btn-info">Edit</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: ['video'],
  head: {
    title: 'Watch'
  }
  // data() {
  //   return {
  //     videos: [
  //       {id: '16', name: 'Intro to NuxtJS'},
  //       {id: '1', name: 'Intro to VueJS'},
  //       {id: '71', name: 'Advanced Techniques for Library X'},
  //     ]
  //   }
  // },
  // computed: {
  //   video() {
  //     return this.videos.find(v => v.id == this.$route.params.id)
  //   }
  // }
}
</script>

<style lang="scss" scoped>

</style>