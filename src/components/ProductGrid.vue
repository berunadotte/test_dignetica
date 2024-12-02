<template>
  <div class="product-grid">
    <ProductCard v-for="product in products" :key="product.id" />
  </div>
</template>

<script>
import ProductCard from './ProductCard.vue'

export default {
  components: { ProductCard },
  data() {
    return {
      products: Array(12).fill({ id: Math.random() }),
    }
  },
}
</script>

<style scoped lang="scss">
.product-grid {
  margin-top: 18px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
}
</style>
