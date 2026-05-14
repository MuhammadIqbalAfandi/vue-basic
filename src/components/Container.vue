<script setup lang="ts">
const props = defineProps<{
  title: string;
}>();
</script>

<template>
  <header>
    <slot name="header"> No header content provided. </slot>
  </header>
  <main>
    <slot name="main"> No content provided. </slot>
  </main>
  <footer>
    <slot name="footer"> No footer content provided. </slot>
  </footer>
</template>
