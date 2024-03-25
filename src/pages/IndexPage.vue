<template>
  <div :class="{ 'q-pa-md': !$q.screen.xs }">
    <div class="q-col-gutter-md row items-start">
      <div v-for="(video, i) in videos" :key="i" class="col-12 col-md-3">
        <VideoCard :data="video" />
      </div>
    </div>
  </div>
</template>

<script setup>
import VideoCard from "../components/VideoCard.vue";

defineOptions({
  name: "IndexPage",
});

const videos = [
  {
    thumbnail_url: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Video 1",
    channel_name: "Channel 1",
    views: 123,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/mountains.jpg",
    title: "Video 2",
    channel_name: "Channel 2",
    views: 224,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/quasar.jpg",
    title: "Video 3",
    channel_name: "Channel 3",
    views: 13,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Video 4",
    channel_name: "Channel 4",
    views: 23,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/quasar.jpg",
    title: "Video 5",
    channel_name: "Channel 5",
    views: 13,
  },

  {
    thumbnail_url: "https://cdn.quasar.dev/img/mountains.jpg",
    title: "Video 6",
    channel_name: "Channel 6",
    views: 224,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Video 7",
    channel_name: "Channel 7",
    views: 23,
  },
  {
    thumbnail_url: "https://cdn.quasar.dev/img/parallax1.jpg",
    title: "Video 8",
    channel_name: "Channel 8",
    views: 123,
  },
];
</script>
