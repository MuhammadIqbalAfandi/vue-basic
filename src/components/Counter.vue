<script setup lang="ts">
import { ref, type Ref } from "vue";

const count: Ref<{ id: number; name: string[] }> = ref({
  id: 0,
  name: [],
});

function increment(): void {
  count.value.id++;
  count.value.name.push(`Name ${count.value.id}`);
}
</script>

<template>
  <h1>
    Counter: {{ count.id }} <br />
    {{ count.name.join(", ") }}
  </h1>
  <button @click="increment">Increment</button>
</template>
