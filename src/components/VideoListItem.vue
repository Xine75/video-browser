<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" :src="thumbnailUrl" />
    <div class="media-body"></div>
    {{ video.snippet.title }}
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    //use "this." to reference a prop inside a component
    thumbnailUrl(){
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    }
  }
};
</script>

<style scoped>
li {
  display:flex;
  cursor: pointer;
}
li:hover {
  background-color: #eee;
}
.media-body {
  margin-left: 3%;
}
</style>