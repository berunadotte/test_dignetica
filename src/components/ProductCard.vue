<template>
  <div class="product-card">
    <div class="hot-sale-badge">
      Хит продаж
      <img class="hot-sale-badge-logo" src="../assets/fire-logo.svg" alt="product without image">
    </div>
    <div class="product-card-image-wrapper">
      <img v-if="isAvailable" class="product-card-image" src="../assets/box-logo.svg" alt="product without image">
      <img v-else class="product-card-image-empty" src="../assets/box-logo.svg" alt="product without image">
    </div>
    <div class="sale-badge">25%</div>
    <p class="brand-name">Бренд</p>
    <p class="product-description">Полное название товара в несколько строк для вида с обрывом в конце...</p>

    <div v-if="isAvailable" class="price-wrapper">
      <p class="price">5 990 ₽</p>
      <p class="old-price">5 990 ₽</p>
    </div>
    <button v-if="isAvailable" class="checkout-button">Купить</button>
    <button v-else class="notify-button">Сообщить о поступлении</button>
  </div>

</template>

<script>
export default {
  data() {
    return {
      isAvailable: true,
    };
  },
  mounted() {
  this.isAvailable = Math.random() > 0.5;
}
};
</script>

<style scoped lang="scss">
@import '../assets/styles/mixins.scss';
.product-card {
  position: relative;
  font-family: $font-family;
  text-align: center;
  width: 333px;
  height: 372px;
  background-color: $primary-color;
}

.product-card-image-wrapper {
  @include flex-center;
  justify-content: center;
  width: 100%;
  height: 200px;
  background-color: #F8F8FA;
  overflow: hidden;
  transition: 0.3s;
  cursor: pointer;
  &:hover {
    .product-card-image, .product-card-image-empty {
      transform: scale(1.2);
      transition: 0.3s;
    }
  }
  .product-card-image-empty {
      opacity: 0.5;
  }
}

.sale-badge {
  @include flex-center;
  position: absolute;
  width: 48px;
  height: 26px;
  border-radius: 4px;
  background-color: $secondary-color;
  color: $primary-color;
  justify-content: center;
  font-size: 14px;
  line-height: 14;
  margin-left: 12px;
  margin-top: -38px;
}

.hot-sale-badge {
  position: absolute;
  width: 112px;
  height: 32px;
  margin-top: 12px;
  margin-left: 12px;
  border: 1px solid #F2F2F2;
  border-radius: 4px;
  background-color: $primary-color;
  font-size: 14px;
  line-height: 16px;
  z-index: 1;

   .hot-sale-badge-logo {
      position: relative;
      top: 4px;
   }
}

.brand-name {
  font-size: 14px;
  line-height: 16px;
  color: $gray;
  font-weight: 400;
  align-self: center;
  justify-self: start;
  margin-top: 16px;
  margin-bottom: 8px;
}

.product-description {
  text-align: start;
  font-size: 14px;
  line-height: 16px;
  margin: 0;
  transition: color 0.3s ease;
  &:hover {
    cursor: pointer;
    color: $secondary-color;
  }
}

.price-wrapper {
  @include flex-center;
  justify-content: start;

  .price {
    font-size: 16px;
    line-height: 14px;
    font-weight: 700;
  }

  .old-price {
    text-decoration: line-through;
    color: $gray;
    margin-left: 8px;
    font-size: 12px;
    line-height: 14px;
  }
}

.checkout-button {
  position: absolute;
  left: 0px;
  width: 75px;
  height: 38px;
  border: 1px solid $secondary-color;
  border-radius: 4px;
  background-color: $primary-color;
  color: $secondary-color;
  transition: color 0.3s ease;
  transition: background-color 0.3s ease;

  &:hover {
    cursor: pointer;
    background-color: $secondary-color;
    color: $primary-color;
  }
}

.notify-button {
  position: absolute;
  left: 0px;
  width: 100%;
  height: 38px;
  border: 1px solid $gray;
  border-radius: 4px;
  background-color: $primary-color;
  color: $gray;
  transition: color 0.3s ease;
  transition: background-color 0.3s ease;
  margin-top: 62px;

  &:hover {
    cursor: pointer;
    background-color: $gray;
    color: $primary-color;
  }
}
</style>