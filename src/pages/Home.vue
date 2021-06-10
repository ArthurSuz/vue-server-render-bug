<template>
  <div :data-test="test">{{ test }}</div>
</template>

<script setup>
import { computed } from "vue";
const test = computed(() => {
  let data = Math.random();
  console.log("data", data);
  return data;
});
</script>
