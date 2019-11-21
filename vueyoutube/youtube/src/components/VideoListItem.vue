<template>
<div>
    <li class="list-group-item my-3" @click="selectedVideo,scrollToTop">
        <h3>{{ video.snippet.title }}</h3>
        <p>{{ video.snippet.description }}</p>
        <img :src="video.snippet.thumbnails.high.url" alt="">
    </li>
</div>
</template>

<script>
export default {
    name:'VideoListItem',
    props:{
        video:{
            type: Object,
            required: true
        }
    },  
    methods: { 
        scrollToTop() {
            window.scrollTo(0,0);
        },
        selectedVideo() {        
            // video select-event $emit
            this.$emit('video-select-event', this.video)
        }
    },
}
</script>

<style scoped>
img {
    width: 360px;
}
li {
    cursor: pointer;
}
li:hover {
    background-color: #fffff2;
}
</style>