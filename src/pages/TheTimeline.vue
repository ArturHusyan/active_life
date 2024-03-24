<script setup>
import TimelineItem from '../components/TimelineItem.vue';
import { generateTimelineItems } from '../functions';

</script>

<template>
  <div class="mt-7">
    <ul>
      <TimelineItem
        v-for="timelineItem in generateTimelineItems()"
        :key="timelineItem.hour"
        :timeline-item="timelineItem"
      />
    </ul>
  </div>
</template>
