<script setup lang="ts">
import ProductCard from "./ProductCard.vue";

const products: {
  id: number;
  name: string;
  price: number;
  inStock: boolean;
}[] = [
  {
    id: 1,
    name: "Laptop",
    price: 15000000,
    inStock: true,
  },
  {
    id: 2,
    name: "Keyboard",
    price: 500000,
    inStock: false,
  },
];
</script>

<template>
  <div class="container">
    <ProductCard
      v-for="product in products"
      :key="product.id"
      :name="product.name"
      :price="product.price"
      :in-stock="product.inStock"
    />
  </div>
</template>
