<script setup lang="ts">
import { nextTick, ref, type Ref } from "vue";

const showInput = ref(false);
const inputRef: Ref<HTMLInputElement | null> = ref(null);

async function openInput(): Promise<void> {
  showInput.value = true;
  await nextTick();
  inputRef.value?.focus();
}
</script>

<template>
  <button @click="openInput">Open</button>

  <input type="text" v-if="showInput" ref="inputRef" />
</template>
