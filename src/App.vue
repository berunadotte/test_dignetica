<template>
  <div id="app">
    <Header />
    <CatalogView />
  </div>
</template>

<script>
import Header from './components/HeaderTop.vue';
import CatalogView from './views/CatalogView.vue';

export default {
  components: { Header, CatalogView },
};
</script>