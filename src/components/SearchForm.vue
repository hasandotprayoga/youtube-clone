<template>
  <div class="flex" :style="{ gap: $q.screen.xs ? 0 : '8px' }">
    <div class="search-form row no-wrap" :class="{ dark: $q.dark.isActive }">
      <div style="flex-grow: 1">
        <q-input
          v-model="q"
          placeholder="Search"
          dense
          borderless
          type="search"
          clearable
          clear-icon="close"
          class="q-pr-sm q-pl-md"
          @focus="isOnFocus = true"
          @blur="isOnFocus = false"
        />
      </div>
      <q-btn
        padding="xs md"
        square
        flat
        icon="search"
        class="search-button"
        :class="{ 'dark-button': $q.dark.isActive }"
        style="background-color: #f8f8f8; color: black"
      />
    </div>

    <div>
      <q-btn flat round :class="$q.dark.isActive ? 'white' : 'icon-light'">
        <q-icon name="mic" />
      </q-btn>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const isOnFocus = ref(false);

const q = ref(null);
</script>

<style scoped>
.search-form {
  flex-grow: 1;
  border-color: #d3d3d3;
  border-width: 1px;
  border-style: solid;
  border-radius: 9999px;

  .dark-button {
    border-color: #303030 !important;
    background-color: #222222 !important;
    color: white !important;
  }

  .search-button {
    border-width: 1px;
    border-style: solid;
    border-radius: 9999px;
    border-color: #d3d3d3;
  }
}

.search-form.dark {
  border-color: #303030 !important;
}
</style>
