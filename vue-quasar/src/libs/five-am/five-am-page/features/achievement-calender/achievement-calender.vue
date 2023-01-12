<template>
  <div class="q-pa-md">
    <div class="text-subtitle1">Date achieved (5 AM Project)</div>
    <q-date v-model="date" :events="eventsFn" :event-color="'teal'" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const currentDate = new Date();
const currentDatePopulated = `${currentDate.getFullYear()}/${
  currentDate.getMonth() + 1
}/${currentDate.getDate() + 1}`;

//TODO: Get AchivedDates from API
const achievedDates = ['2023/01/12'];
const date = ref(currentDatePopulated);
const eventsFn = (date: string) => {
  return achievedDates.includes(date);
};
</script>
