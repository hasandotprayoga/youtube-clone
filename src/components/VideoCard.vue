<template>
  <div class="flex" style="flex-direction: column; gap: 12px">
    <q-img
      :src="data.thumbnail_url"
      :style="{ 'border-radius': $q.screen.xs ? 0 : '8px' }"
      :ratio="16 / 9"
    />
    <div class="flex" style="gap: 12px" :class="{ 'q-px-md': $q.screen.xs }">
      <q-avatar size="32px">
        <img src="https://cdn.quasar.dev/img/avatar.png" />
      </q-avatar>
      <div class="flex" style="flex-direction: column; gap: 8px">
        <div class="text-h6" style="line-height: 1rem">{{ data.title }}</div>
        <div :style="{ color: $q.dark.isActive ? '#fff' : '#606060' }">
          <div>{{ data.channel_name }}</div>
          <div>{{ data.views }} views</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  data: Object,
});
</script>
