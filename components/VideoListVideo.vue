<template>
  <v-card width="340px"
          hover
          class="ma-2"
          >
          <!-- :to="{ name: 'video-watch', params: { id: video.id1}}" -->
    <v-img :src="video.thumbnail"></v-img>
    <div>image</div>
    <v-card-title>{{ video.name }}</v-card-title>
    <v-card-text>
      <!-- <div class="green--text" v-if="isPlayed(video.id1)">
        <font-awesome-icon icon="check"> Played
      </div> -->
    </v-card-text>

    <v-card-action>
      <span v-for="tag_id in video.tag_ids" :key="`${video.id1}-${tag_id}`">
        <v-btn color="green lighten-2"
              class="mr-2"
              small
              @mousedown.stop
              :to="{ name: 'tag', params: { id: tag_id }}">
              {{ getTag(tag_id).name }}
        </v-btn>
      </span>
    </v-card-action>
  </v-card>
</template>

<script>
// import { mapGetters } from 'vuex';
export default {
  // computed: {
  //   ...mapGetters({
  //     getTags: 'tags/get',
  //     isPlayed: 'users/videoIsPlayed'
  //   })
  // },
  props: ['video'],
}
</script>

<style lang="scss" scoped>

</style>