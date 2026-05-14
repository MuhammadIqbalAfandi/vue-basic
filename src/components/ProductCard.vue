<script setup lang="ts">
const props = defineProps<{
  name: string;
  price: number;
  inStock: boolean;
}>();
</script>

<template>
  <div class="card">
    <h2>{{ name }}</h2>

    <p>Rp {{ price }}</p>

    <p v-if="inStock">Available</p>

    <p v-else>Out of Stock</p>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid #ccc;
  padding: 16px;
  width: 200px;
  border-radius: 8px;
}
</style>
