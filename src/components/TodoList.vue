<script setup lang="ts">
const fruits: string[] = ["Apple", "Banana", "Cherry"];
const user = {
  name: "Iqbal",
  age: 28,
  city: "Medan",
};
const categories = [
  {
    name: "Fruits",
    items: ["Apple", "Orange"],
  },
  {
    name: "Drinks",
    items: ["Tea", "Coffee"],
  },
];
</script>

<template>
  <ul>
    <li v-for="(fruit, index) in fruits">{{ index }} - {{ fruit }}</li>
  </ul>

  <ul>
    <li v-for="(value, key) in user">{{ key }} : {{ value }}</li>
  </ul>

  <ul>
    <li v-for="(value, key, index) in user" :key="index">
      {{ index }} - {{ key }} : {{ value }}
    </li>
  </ul>

  <ul>
    <li v-for="n in 10">
      {{ n }}
    </li>
  </ul>

  <div v-for="category in categories" :key="category.name">
    <h2>{{ category.name }}</h2>

    <ul>
      <li v-for="item in category.items">
        {{ item }}
      </li>
    </ul>
  </div>
</template>
