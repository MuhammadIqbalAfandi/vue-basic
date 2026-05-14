<script setup lang="ts">
import Container from "./components/Container.vue";
</script>

<template>
  <Container title="My Website">
    <template #header>
      <h1>My Website</h1>
    </template>
    <template #main>
      <p>Welcome to my website!</p>
    </template>
    <template #footer>
      <p>Copyright 2024</p>
    </template>
  </Container>
</template>

<style></style>
