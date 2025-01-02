<script setup lang="ts">
import { ref } from 'vue';
import GetLocation from './components/GetLocation.vue';
import WeatherReport from './components/WeatherReport.vue';

const coords = ref();

const updateCoords = (location: { latitude: number; longitude: number }) => {
  coords.value = location;
};
</script>

<template>
  <div>
    <GetLocation @update-coords="updateCoords" />
    <WeatherReport v-if="coords" :coords="coords" />
  </div>
</template>
