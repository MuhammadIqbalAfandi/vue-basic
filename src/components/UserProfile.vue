<script setup lang="ts">
import { inject } from "vue";

type User = {
  id: number;
  name: string;
  email: string;
};

const user = inject<User>("user");

if (!user) {
  throw new Error("User not found");
}
</script>

<template>
  <div class="card">
    <h1>{{ user.name }}</h1>
    <p>{{ user.email }}</p>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid #ccc;
  padding: 16px;
  margin-top: 16px;
}
</style>
