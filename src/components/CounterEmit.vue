<script setup lang="ts">
const emit = defineEmits<{
  increase: [];
}>();

function handleClick() {
  emit("increase");
}
</script>

<template>
  <button @click="handleClick">Increase</button>
</template>
