<script setup lang="ts">
import Container from "./components/Container.vue";
import UserProfileApp from "./components/UserProfileApp.vue";
</script>

<template>
  <Container title="My Website">
    <template #main>
      <UserProfileApp />
    </template>
    <template #footer>
      <p>Copyright 2024</p>
    </template>
  </Container>
</template>

<style></style>
