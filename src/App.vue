<script setup>
import { ref, onMounted } from "vue";

const today = ref(null);
const is_loading = ref(true);

onMounted(() => {
  today.value = `${new Date().getFullYear()}-${new Date().getMonth() + 1}-${new Date().getDate()}`;
  window.open(`https://app.dailybot.com/checkins/response-daily/b1d16ce3-7aea-48ee-96d0-406a17e2bae4/add/${today.value}`, '_self');
  // window.open(`https://app.dailybot.com/checkins/response-daily/b1d16ce3-7aea-48ee-96d0-406a17e2bae4/add/${today.value}`, '_blank');
  setTimeout(() => {
    is_loading.value = false;
  }, 2000);
});
</script>

<template>
  <div class="app">
    <div v-if="is_loading">loading...</div>
    <div v-else>
      <b>Today:</b> {{ today }}
    </div>
  </div>
</template>
