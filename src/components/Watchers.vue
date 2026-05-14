<script setup lang="ts">
import { onWatcherCleanup, ref, watchEffect, type Ref } from "vue";

const productId: Ref<string> = ref("product1");
const product: Ref<{
  id: string;
  name: string;
  description: string;
  price: number;
} | null> = ref(null);

// watch(
//   productId,
//   async (newVal, _) => {
//     if (newVal) {
//       try {
//         const response = await fetch(`/public/` + `${newVal}.json`);
//         if (response.ok) {
//           product.value = await response.json();
//         } else {
//           console.error("Failed to fetch product data:", response.statusText);
//           product.value = null;
//         }
//       } catch (error) {
//         console.error("Error fetching product data:", error);
//         product.value = null;
//       }
//     }
//   },
//   { immediate: true },
// );

watchEffect(async () => {
  onWatcherCleanup(() => {
    console.log("Cleaning up watcher...");
  });

  try {
    const response = await fetch(`/public/` + `${productId.value}.json`);
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
});
</script>

<template>
  <label for="product"
    >Product Id:
    <select id="product" v-model="productId">
      <option value="product1">Product 1</option>
      <option value="product2">Product 2</option>
      <option value="product3">Product 3</option>
    </select>
  </label>

  <div v-if="product">
    <h1>{{ product.name }}</h1>
    <p>{{ product.description }}</p>
    <p>Price: ${{ product.price }}</p>
  </div>
</template>
