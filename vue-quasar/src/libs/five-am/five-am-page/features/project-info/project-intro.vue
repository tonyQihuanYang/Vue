<template>
  <q-card dark bordered>
    <q-card-section>
      <div class="text-h6">5 AM Project</div>
      <div class="text-subtitle2">
        This project is to record the achieved dates that trying to join
        <a href="https://www.beautybrainuk.com/blogs/blog/5-am-club"
          >5am club</a
        >
        since 2023/01/12.
      </div>
    </q-card-section>

    <q-separator dark inset />

    <q-card-actions class="justify-end">
      <q-btn
        flat
        icon="event"
        color="primary"
        :disable="isTodayAchived"
        @click="achieveToday"
        >{{ achieveButtonText }}</q-btn
      >
    </q-card-actions>
  </q-card>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue';
const BTN_DISPLAY_TEXT = {
  NotAchivedToday: 'Achive Today',
  AchivedToday: 'Already Achived Today',
};
const isTodayAchived = ref(false);
const achieveButtonText = computed(() =>
  isTodayAchived.value
    ? BTN_DISPLAY_TEXT.AchivedToday
    : BTN_DISPLAY_TEXT.NotAchivedToday
);
const achieveToday = () => {
  console.log('Successfully Achived Today');
  isTodayAchived.value = true;
  //TODO: Connect to API
};
</script>
