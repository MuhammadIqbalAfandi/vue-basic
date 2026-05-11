<script setup lang="ts">
import { reactive, type Reactive } from "vue";

const person: Reactive<{ firstName: string; lastName: string }> = reactive({
  firstName: "",
  lastName: "",
});

function sayHello(): void {
  person.firstName = (
    document.getElementById("firstName") as HTMLInputElement
  ).value;
  person.lastName = (
    document.getElementById("lastName") as HTMLInputElement
  ).value;
}
</script>

<template>
  <form @submit.prevent="sayHello">
    <input type="text" placeholder="Enter your name" id="firstName" />
    <br />
    <input type="text" placeholder="Enter your last name" id="lastName" />
    <br />
    <button type="submit">Say Hello</button>
  </form>

  <h1>Hello, {{ person.firstName }} {{ person.lastName }}</h1>
</template>
