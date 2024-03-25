<template>
  <q-layout view="hHh Lpr lff">
    <q-header :class="$q.dark.isActive ? 'bg-dark' : 'bg-light'">
      <q-toolbar
        class="justify-between"
        :style="{ gap: $q.screen.xs ? '4px' : '16px' }"
      >
        <div class="flex items-center" style="gap: 16px">
          <div v-if="!$q.screen.xs">
            <q-btn
              flat
              round
              dense
              :class="$q.dark.isActive ? 'white' : 'icon-light'"
              @click="drawer = !drawer"
            >
              <q-icon name="menu" />
            </q-btn>
          </div>
          <YoutubeLogo
            :style="{
              height: '60px',
              width: '90px',
              color: $q.dark.isActive ? 'white' : '#212121',
            }"
          />
        </div>

        <q-space v-if="$q.screen.xs" />

        <SearchWrapper />

        <div class="flex" style="gap: 4px">
          <q-btn
            flat
            round
            dense
            :class="$q.dark.isActive ? 'white' : 'icon-light'"
          >
            <q-icon name="more_vert" />
          </q-btn>
          <AccountButton />
          <q-btn
            flat
            round
            dense
            :class="$q.dark.isActive ? 'white' : 'icon-light'"
            @click="$q.dark.toggle()"
          >
            <q-icon name="invert_colors" />
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="drawer"
      show-if-above
      :width="80"
      :breakpoint="500"
      :class="$q.dark.isActive ? 'bg-dark' : 'bg-light'"
    >
      <q-scroll-area class="fit" :horizontal-thumb-style="{ opacity: 0 }">
        <q-list padding>
          <q-item clickable v-ripple>
            <q-item-section avatar class="items-center">
              <q-icon name="home" />
              <q-item-section> Home </q-item-section>
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar class="items-center">
              <q-icon name="music_video" />
              <q-item-section> Short </q-item-section>
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar class="items-center">
              <OndemandIcon
                :style="{
                  color: $q.dark.isActive ? 'white' : 'black',
                  'font-size': '24px',
                }"
              />
              <q-item-section> Video </q-item-section>
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar class="items-center">
              <q-icon name="video_library" filled />
              <q-item-section> Library </q-item-section>
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar class="items-center">
              <q-icon name="history" filled />
              <q-item-section> History </q-item-section>
            </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import YoutubeLogo from "components/YoutubeLogo.vue";
import SearchWrapper from "components/SearchWrapper.vue";
import AccountButton from "components/AccountButton.vue";
import OndemandIcon from "components/icons/OndemandIcon.vue";

const drawer = ref(false);
</script>
