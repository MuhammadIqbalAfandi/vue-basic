<script setup lang="ts">
import { computed, reactive, type Reactive } from "vue";

const person: Reactive<{
  firstName: string;
  lastName: string;
}> = reactive({
  firstName: "",
  lastName: "",
});

function firstNameChange(event: Event) {
  person.firstName = (event.target as HTMLInputElement).value;
}

function lastNameChange(event: Event) {
  person.lastName = (event.target as HTMLInputElement).value;
}

const fullName = computed(() => `${person.firstName} ${person.lastName}`);
</script>

<template>
  <form>
    <input
      type="text"
      placeholder="first name"
      name="firstName"
      @input="firstNameChange"
    />
    <br />
    <input
      type="text"
      placeholder="last name"
      name="lastName"
      @input="lastNameChange"
    />
  </form>

  <h1>Your Full Name is: {{ fullName }}</h1>
</template>
