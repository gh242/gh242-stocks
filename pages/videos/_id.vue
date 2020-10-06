<template>
  <div>
    <nuxt-child :video="video" />
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  head() {
    return {
      title: '',
      // titleTemplate: `%s ${this.video.name} - vue`
      titleTemplate: `%s ${this.video.name} - vue`
    }
  },
  // async asyncData(context) {
  // async asyncData({$axios, params}) {
  async fetch({$axios, params, store}) {
    // console.log(context.params.id);
    // let response = await context.$axios.get(`http://gh242-test2.herokuapp.com/api/posts`)
    let response = await $axios.get(`/posts`)
    // let video = response.data.find(v => v.id1 == context.params.id)
    let video = response.data.find(v => v.id1 == params.id)
    console.log(video);

    store.commit('SET_CURRENT_VIDEO', video);
    // let video = reponse.data;
    // return {
    //   video
    // } 
  },
  computed: {
    ...mapState({
      video: 'currentVideo'
    })
    // video() {
    //   return this.$store.state.currentVideo
    // }
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