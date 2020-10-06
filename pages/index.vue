<template>
  <div class="home">
    <div class="display-4 ma-4 d-flex justify-center">
      All Videos
    </div>

    <div class="d-flex flex-wrap">
      <div v-for="video in videos" :key="video.name">
        <!-- {{ video.name }} -->
        <VideoListVideo :video="video"></VideoListVideo>
      </div>
    </div>
  </div>
</template>

<script>
import VideoListVideo from '../components/VideoListVideo'
export default {
  components: {
    VideoListVideo
  },
  async asyncData({$axios}) {
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
    return {
      videos
    }
  }
}
</script>

<style>
/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
} */

/* .title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
} */
</style>
