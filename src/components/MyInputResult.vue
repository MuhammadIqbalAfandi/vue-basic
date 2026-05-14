<script setup lang="ts">
const input = defineModel<string>("input");
</script>

<template>
  <p v-if="input">{{ input }}</p>
  <p v-else>No input provided</p>
</template>
