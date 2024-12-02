<template>
  <div class="catalog container">
    <SidebarFilter />
    <ProductGrid />
  </div>
</template>

<script>
import SidebarFilter from '../components/SidebarFilter.vue';
import ProductGrid from '../components/ProductGrid.vue';

export default {
  components: { SidebarFilter, ProductGrid },
};
</script>

<style scoped lang="scss">
.catalog {
  display: flex;
  gap: 36px;
}
</style>