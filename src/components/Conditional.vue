<script setup lang="ts">
import { ref, type Ref } from "vue";

const show: Ref<boolean> = ref(true);
const role: Ref<string> = ref("staff");
const visible: Ref<boolean> = ref(true);
</script>

<template>
  <h1 v-if="show">Welcome</h1>

  <button @click="show = !show">Toggle</button>

  <h1 v-if="role === 'admin'">Admin</h1>
  <h1 v-else-if="role === 'staff'">Staff</h1>
  <h1 v-else>Access Denied</h1>

  <p v-show="visible">Hello</p>
</template>
