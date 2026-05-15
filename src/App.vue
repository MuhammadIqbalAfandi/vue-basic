<script setup lang="ts">
import Container from "./components/Container.vue";
import EmitApp from "./components/EmitApp.vue";
</script>

<template>
  <Container title="My Website">
    <template #main>
      <EmitApp />
    </template>
    <template #footer>
      <p>Copyright 2024</p>
    </template>
  </Container>
</template>

<style></style>
