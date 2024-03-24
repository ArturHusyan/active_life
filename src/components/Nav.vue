<script setup>
import NavItem from './NavItem.vue';
import {NAV_ITEMS} from '../constants';

defineProps(['currentPage']);
const emit = defineEmits(['navigate']);

</script>

<template>
  <nav class="sticky bottom-0 z-20 bg-indigo-800 text-white">
    <ul class="flex justify-around atems-center">
      <NavItem 
        v-for="icon, page in NAV_ITEMS" 
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
