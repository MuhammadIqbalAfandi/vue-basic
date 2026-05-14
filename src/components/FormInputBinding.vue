<script setup lang="ts">
import { reactive, type Reactive } from "vue";

const contact: Reactive<{
  name: string;
  message: string;
  married: boolean;
  hobies: string[];
  gender: boolean;
  city: string;
  age: number;
  favoriteColor: string[];
}> = reactive({
  name: "",
  message: "",
  married: false,
  hobies: [],
  gender: false,
  city: "",
  age: 0,
  favoriteColor: [],
});
</script>

<template>
  <form>
    <label for="name">Name: </label>
    <input type="text" id="name" placeholder="name" v-model="contact.name" />
    <br />
    <label for="message">Message: </label>
    <textarea
      id="message"
      placeholder="message"
      v-model="contact.message"
    ></textarea>
    <br />
    <label for="married">Married: </label>
    <input
      type="checkbox"
      id="married"
      placeholder="married"
      v-model="contact.married"
    />
    <br />
    <label>Hobbies: </label>
    <label for="football"
      >Football
      <input
        type="checkbox"
        id="football"
        placeholder="hobbies"
        v-model="contact.hobies"
      />
    </label>
    <label for="swimming"
      >Swimming
      <input
        type="checkbox"
        id="swimming"
        placeholder="hobbies"
        v-model="contact.hobies"
      />
    </label>
    <br />
    <label>Gender: </label>
    <label for="male">
      Male
      <input
        type="radio"
        id="male"
        name="gender"
        value="male"
        v-model="contact.gender"
      />
    </label>
    <label for="female">
      Female
      <input
        type="radio"
        id="female"
        name="gender"
        value="female"
        v-model="contact.gender"
      />
    </label>
    <br />
    <label for="city">City: </label>
    <select v-model="contact.city">
      <option value="">Select a city</option>
      <option value="new-york">New York</option>
      <option value="london">London</option>
      <option value="tokyo">Tokyo</option>
    </select>
    <br />
    <label for="age">Age: </label>
    <input type="number" id="age" v-model="contact.age" />
    <br />
    <label for="color">Favorite Colors: </label>
    <select multiple v-model="contact.favoriteColor">
      <option value="red">Red</option>
      <option value="blue">Blue</option>
      <option value="green">Green</option>
    </select>
  </form>

  <h1>Contact Information:</h1>
  <p>Name: {{ contact.name }}</p>
  <p>Message: {{ contact.message }}</p>
  <p>Married: {{ contact.married }}</p>
  <p>Hobbies: {{ contact.hobies.join(", ") }}</p>
  <p>Gender: {{ contact.gender }}</p>
  <p>City: {{ contact.city }}</p>
  <p>Age: {{ contact.age }}</p>
  <p>Favorite Colors: {{ contact.favoriteColor.join(", ") }}</p>
</template>
