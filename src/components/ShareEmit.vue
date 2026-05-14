<script setup lang="ts">
interface User {
  id: number;
  name: string;
}

const emit = defineEmits<{
  share: [User];
}>();

const user = {
  id: 1,
  name: "Iqbal",
};
</script>

<template>
  <button @click="emit('share', user)">Share User</button>
</template>
