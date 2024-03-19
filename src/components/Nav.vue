<script setup>
import {ref} from 'vue';
import NavItem from './NavItem.vue';
import {ClockIcon, ListBulletIcon, ChartBarIcon} from '@heroicons/vue/24/outline';

const navItems = {
  timeline: ClockIcon,
  activity: ListBulletIcon,
  progress: ChartBarIcon,
};

const currentPage = ref('timeline');
</script>

<template>
  <nav class="sticky bottom-0 z-20 bg-indigo-800 text-white">
    <ul class="flex justify-around atems-center">
      <NavItem 
        v-for="icon, page in navItems" 
        :key="page"
        :href="`#${page}`"
        :class="{
          'bg-indigo-300 pointer-events-none': page === currentPage,
        }"
        @click="currentPage = page"
      >
        <component :is="icon" class="h-6 w-6" />{{page}}
      </NavItem>
    </ul>
  </nav>
</template>
