<script setup lang="ts">
import { provide } from "vue";
import UserProfile from "./UserProfile.vue";

type User = {
  id: number;
  name: string;
  email: string;
};

const user: User = {
  id: 1,
  name: "John Doe",
  email: "john.doe@example.com",
};

provide("user", user);
</script>

<template>
  <div>
    <h1>App Component</h1>
    <UserProfile />
  </div>
</template>
