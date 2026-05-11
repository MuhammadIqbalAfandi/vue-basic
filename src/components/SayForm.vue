<script setup lang="ts">
import {
  computed,
  reactive,
  ref,
  type ComputedRef,
  type Reactive,
  type Ref,
} from "vue";

const counter: Ref<number> = ref(0);

const person: Reactive<{ firstName: string; lastName: string }> = reactive({
  firstName: "",
  lastName: "",
});

function increment(): void {
  console.log("Counter before increment:", counter.value);
  counter.value++;
}

const fullName: ComputedRef<string> = computed((prev) => {
  console.log("Computing full name with previous value:", prev);
  console.log(`${person.firstName} ${person.lastName}`);
  return `${person.firstName} ${person.lastName}`;
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
  <h1>Counter: {{ counter }}</h1>
  <button @click="increment">Increment</button>

  <form @submit.prevent="sayHello">
    <input type="text" placeholder="Enter your name" id="firstName" />
    <br />
    <input type="text" placeholder="Enter your last name" id="lastName" />
    <br />
    <button type="submit">Say Hello</button>
  </form>

  <h1>Hello, {{ fullName }}</h1>
</template>
