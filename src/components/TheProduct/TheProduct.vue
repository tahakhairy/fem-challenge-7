<template>
  <main class="content">
    <ProductImages @imageId="" />
    <ProductDetails :product="product" />
  </main>
</template>

<script setup>
import { ref } from "vue";
import ProductImages from "./components/ProductImages.vue";
import ProductDetails from "./components/ProductDetails.vue";
import { useProductStore } from "@/stores/product";
import { storeToRefs } from "pinia";

const store = useProductStore();
await store.getData();
const { product } = storeToRefs(store);
</script>

<style lang="scss" scoped>
.content {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  padding: 5rem 0;
}
</style>
