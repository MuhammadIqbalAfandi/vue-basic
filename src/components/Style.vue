<script setup lang="ts">
import { ref, type Ref } from "vue";

const dark: Ref<boolean> = ref(false);
const active: Ref<boolean> = ref(true);

const color: string = "green";
const activeClass: string = "active";
const errorClass: string = "error";
</script>

<template>
  <h1 class="title">Hello vue</h1>
  <h1 :style="{ color: color }">Hello</h1>
  <div
    :style="{
      backgroundColor: dark ? 'black' : 'white',
      color: dark ? 'white' : 'black',
    }"
  >
    Dark Mode
  </div>
  <button @click="dark = !dark">Toggle</button>
  <button :class="{ active: active }">Button</button>
  <div :class="[activeClass, errorClass]">Hello</div>
</template>

<style scoped>
.active {
  background-color: blue;
  color: white;
}
.error {
  background-color: red;
  color: white;
}
.title {
  color: blue;
  font-size: 32px;
}
</style>
