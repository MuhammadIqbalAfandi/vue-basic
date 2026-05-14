<script setup lang="ts">
const props = defineProps<{
  title: string;
}>();
</script>

<template>
  <header v-if="$slots.header">
    <slot name="header"> No header content provided. </slot>
  </header>
  <main v-if="$slots.main">
    <slot name="main"> No content provided. </slot>
  </main>
  <footer v-if="$slots.footer">
    <slot name="footer"> No footer content provided. </slot>
  </footer>
</template>
