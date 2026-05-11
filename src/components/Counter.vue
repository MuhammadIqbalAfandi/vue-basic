<script setup lang="ts">
import { ref, type Ref } from "vue";

const count: Ref<number> = ref(0);

function increment(): void {
  count.value++;
}
</script>

<template>
  <h1>Counter: {{ count }}</h1>
  <button @click="increment">Increment</button>
</template>
