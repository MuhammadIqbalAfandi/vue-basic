<script setup lang="ts">
import { ref } from "vue";
import MyInput from "./MyInput.vue";
import MyInputResult from "./MyInputResult.vue";

const input = ref("");
</script>

<template>
  <MyInputResult v-model:input="input" />
  <MyInput v-model="input" />
</template>
