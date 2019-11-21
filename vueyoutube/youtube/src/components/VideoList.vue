<template>
  <div>
      <h2>영상 목록</h2>
      <ul class="list-group">
    <video-list-item v-for="video in videos" :video="video" :key="video.id.videoId" @video-select-event="selectedVideo" ></video-list-item>
    </ul>
  </div>
</template>
<script>
import VideoListItem from './VideoListItem.vue'
export default {
    name: 'VideoList',
    components:{
        VideoListItem
    },
    props: {
        videos: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            video: []
            } 
    },
    methods: {
        selectedVideo(video) {
            // video select-event $emit
            this.$emit('video-select-event', video)
        }
    },
}
</script>

<style>

</style>