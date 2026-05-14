<script setup lang="ts">
const props = defineProps<{
  title: string;
}>();
</script>

<template>
  <h1>{{ title }}</h1>
  <main>
    <slot />
  </main>
  <footer>
    <p>Copyright 2024</p>
  </footer>
</template>
