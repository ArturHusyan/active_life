<script setup>
import NavItem from './NavItem.vue';
import {PAGE_TIMELINE, PAGE_ACTIVITY, PAGE_PROGRESS} from '../constants.js';
import {ClockIcon, ListBulletIcon, ChartBarIcon} from '@heroicons/vue/24/outline';

defineProps(['currentPage']);
const emit = defineEmits(['navigate']);

const navItems = {
  [PAGE_TIMELINE]: ClockIcon,
  [PAGE_ACTIVITY]: ListBulletIcon,
  [PAGE_PROGRESS]: ChartBarIcon,
};
</script>

<template>
  <nav class="sticky bottom-0 z-20 bg-indigo-800 text-white">
    <ul class="flex justify-around atems-center">
      <NavItem 
        v-for="icon, page in navItems" 
        :key="page"
        :href="`#${page}`"
        :class="{
          'bg-indigo-200 pointer-events-none text-indigo-700': page === currentPage,
        }"
        @click="emit('navigate', page)"
      >
        <component :is="icon" class="h-6 w-6" />{{page}}
      </NavItem>
    </ul>
  </nav>
</template>
