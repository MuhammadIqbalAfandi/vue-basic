<script setup lang="ts">
const hello: string = "<h1>Hello, World!</h1>";
</script>

<template>
  <div class="hello">{{ hello }}</div>
  <div v-html="hello"></div>
</template>

<style scoped>
.hello {
  color: green;
}
</style>
