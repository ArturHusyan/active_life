<script setup>
defineProps(['timelineItem']);
</script>

<template>
    <li
        class="relative flex flex-col gap-2 border-t border-gray-200 py-10 px-4"
      >
        <a 
            href="#"
            :class="[
                'absolute -top-4 left-1/2 -translate-x-1/2 rounded px-2 font-mono text-lg',
                timelineItem.hour === new Date().getHours() ? 'bg-purple-900 text-white' : 'bg-gray-100 text-gray-500'
            ]"
        >
          {{ timelineItem.hour }}:00
        </a>
    </li>
</template>
