<template>
  <div class="container">
    <nuxt-child/>
    <h1>Videos index.vue</h1>
    <div v-for="video in $store.state.videos" :key="video.id1">
      <nuxt-link :to="`/videos/${video.id1}`">{{ video.name }}</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Vue - Video List'
  },
  // async asyncData(context) {
  // async asyncData({$axios}) {
  async fetch({$axios, store}) {
    // let response = await context.$axios.get('http://localhost:3000/api/videos')
    // console.log(response)
    let response = await $axios.get('/posts')
    // let response = await context.$axios.get('http://gh242-test2.herokuapp.com/api/posts')
    console.log(response.data)
    // console.log("response.data= " + response)
    let videos = response.data.map(v=> {
        console.log('v= '+ v.id1);
        console.log('v= '+ v.name);
        return v
      }
    );

    store.commit('SET_VIDEOS', videos);
    // return {
    //   videos
    // }

    // console.log(videos);
    // console.log(videos.type);
    // debugger

    // return {
    //   videos: [
    //     {id: '16', name: 'Intro to NuxtJS'},
    //     {id: '1', name: 'Intro to VueJS'},
    //     {id: '71', name: 'Advanced Techniques for Library X'},
    //   ]
    // }
  },
}
</script>

<style lang="scss" scoped>

</style>