<script setup>
import {CheckCircleIcon} from '@heroicons/vue/24/solid';
</script>

<template>
  <header class="sticky top-0 z-20 flex items-center justify-between border-b bg-indigo-200 p-2">
    <a href="#" class="flex items-center">
      <img src="../assets/img/logo.png" alt="Logo" class="h-10">
      <span class="text-indigo-700 text-lg ml-1">ActiveLife</span>
    </a>
    <a href="#">
      <div 
        v-if="true"
        class="flex items-center gap-1"
      >
        <CheckCircleIcon class="h-6 text-green-600"/>
        <span class="text-green-700 text-sm">Day complete!</span>
      </div>
      <div
        v-else
        class="flex items-center gap-1"
      >
        <div class="h-3 w-3 rounded-full bg-red-500"></div>
        <div class="text-sm">Progress: <span class="font-mono">20%</span></div>
      </div>
    </a>
  </header>
</template>
