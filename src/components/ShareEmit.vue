<script setup lang="ts">
interface User {
  id: number;
  name: string;
}

const user: User = {
  id: 1,
  name: "Iqbal",
};
</script>

<template>
  <button @click="$emit('share', user)">Share User</button>
</template>
