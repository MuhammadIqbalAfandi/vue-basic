<script setup lang="ts">
const hello: string = "<h1>Hello, World!</h1>";
const classHello: string = "hello";
const buttonDisabled: boolean = true;
const styleHello: object = {
  class: "hello",
  id: "hello",
};
</script>

<template>
  <div v-bind:class="classHello">{{ hello }}</div>
  <div :class="classHello" v-html="hello"></div>
  <div v-bind="styleHello">{{ hello }}</div>
  <br />
  <button :disabled="buttonDisabled">Click me</button>
</template>

<style scoped>
#hello {
  font-style: italic;
}
.hello {
  color: green;
}
</style>
