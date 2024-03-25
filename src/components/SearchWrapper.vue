<template>
  <div class="flex" :style="{ gap: $q.screen.xs ? 0 : '8px' }">
    <div v-if="$q.screen.xs">
      <q-btn
        flat
        round
        :class="$q.dark.isActive ? 'white' : 'icon-light'"
        @click="dialog = !dialog"
      >
        <q-icon name="search" />
      </q-btn>

      <q-dialog v-model="dialog" position="top">
        <q-card
          class="q-py-sm q-px-sm flex items-center"
          style="width: 100%; gap: 8px"
        >
          <q-icon
            name="keyboard_backspace"
            style="font-size: 24px"
            v-close-popup
          />
          <SearchForm style="flex-grow: 1" />
        </q-card>
      </q-dialog>
    </div>
    <SearchForm v-else style="min-width: 600px" />
  </div>
</template>

<script setup>
import { ref } from "vue";

import SearchForm from "components/SearchForm.vue";

const dialog = ref(false);
</script>
