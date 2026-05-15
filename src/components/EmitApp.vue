<script setup lang="ts">
import { ref, type Ref } from "vue";
import ShareEmit from "./ShareEmit.vue";
import CounterEmit from "./CounterEmit.vue";

const counter: Ref<number> = ref(0);

function handleIncrease() {
  counter.value++;
}

type User = {
  id: number;
  name: string;
};
</script>

<template>
  <p>{{ counter }}</p>
  <CounterEmit @increase="handleIncrease" />
  <ShareEmit @share="(user: User) => console.log('Selected user:', user)" />
</template>
