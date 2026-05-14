<script setup lang="ts">
import { ref, watch, type Ref } from "vue";

const productId: Ref<string> = ref("");
const product: Ref<{
  id: number;
  name: string;
  description: string;
  price: number;
} | null> = ref(null);

watch(productId, async (newVal, _) => {
  if (newVal) {
    try {
      const response = await fetch(`/public/` + `product${newVal}.json`);
      if (response.ok) {
        product.value = await response.json();
      } else {
        console.error("Failed to fetch product data:", response.statusText);
        product.value = null;
      }
    } catch (error) {
      console.error("Error fetching product data:", error);
      product.value = null;
    }
  }
});
</script>

<template>
  <label for="product"
    >Product Id:
    <select id="product" v-model="productId">
      <option value="1">Product 1</option>
      <option value="2">Product 2</option>
      <option value="3">Product 3</option>
    </select>
  </label>

  <div v-if="product">
    <h1>{{ product.name }}</h1>
    <p>{{ product.description }}</p>
    <p>Price: ${{ product.price }}</p>
  </div>
  <div v-else>
    <p>Please select a product to see its details.</p>
  </div>
</template>
