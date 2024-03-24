<script setup>
import { ref } from 'vue';
import { PAGE_ACTIVITY, PAGE_PROGRESS, PAGE_TIMELINE } from './constants'
import {normalizePageHash} from './functions'
import Header from './components/Header.vue'
import Nav from './components/Nav.vue'
import TheTimeline from './pages/TheTimeline.vue'
import TheActivity from './pages/TheActivity.vue'
import TheProgress from './pages/TheProgress.vue'

const currentPage = ref(normalizePageHash());

function goTo(page) {
  currentPage.value = page;
}
</script>

<template>
  <Header
    @go-to-timeline="goTo(PAGE_TIMELINE)"
    @go-to-progress="goTo(PAGE_PROGRESS)"
  />

  <main class="flex flex-col flex-grow">
    <TheTimeline v-show="currentPage === PAGE_TIMELINE" />
    <TheActivity v-show="currentPage === PAGE_ACTIVITY" />
    <TheProgress v-show="currentPage === PAGE_PROGRESS" />
  </main>

  <Nav
    :current-page="currentPage"
    @navigate="goTo($event)"
  />
</template>
