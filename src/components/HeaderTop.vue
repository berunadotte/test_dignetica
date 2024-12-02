<template>
  <header class="header">
    <div class="container">
      <img src="../assets/logo.svg" class="header_logo" alt="logo" />
      <button class="header_button">Каталог</button>
      <div class="search_container">
        <img
          src="../assets/search-logo.svg"
          alt="search logo"
          class="search_logo"
        />
        <input
          type="text"
          placeholder="Поиск по 100 000 товаров"
          class="search_input"
        />
      </div>
      <nav class="nav_container">
        <a class="nav_container_link" href="#">Информация о компании</a>
        <a class="nav_container_link" href="#">Контакты</a>
        <a class="nav_container_link" href="#">Полезные ссылки</a>
      </nav>
    </div>
  </header>
</template>

<style scoped lang="scss">
@import '../assets/styles/mixins.scss';
.container {
  @include flex-center;
}

.nav_container {
  margin-left: 24px;

  .nav_container_link {
    color: #000;
    text-decoration: none;
    font-size: 14px;
    font-weight: 400;
    font-family: $font-family-header;

    &:nth-child(n + 2) {
      margin-left: 20px;
    }
    &:hover {
      color: $font-hover;
    }
  }
}

.header {
  background-color: white;
  padding: 1rem 0;

  .header_logo {
    margin: 0;
  }

  .header_button {
    font-family: $font-family;
    font-weight: 500;
    font-style: 14px;
    line-height: 17px;
    width: 104px;
    height: 48px;
    border: 1px solid $border-color;
    background-color: $primary-color;
    border-radius: 8px;
    margin-left: 8px;
    transition: 0.3s;
    &:hover {
      color: $primary-color;
      background-color: $secondary-color;
      border: 1px solid $primary-color;
    }
  }

  .search_container {
    @include flex-center;
    height: 48px;
    margin-left: 24px;
    width: 60%;
    border: 1px solid $border-color;
    border-radius: 10px;

    .search_logo {
      width: 24px;
      height: 24px;
      margin-left: 16px;
    }
    .search_input {
      width: 90%;
      height: 100%;
      border: none;
      padding: 0;
      margin-left: 8px;
      &:hover {
        cursor: pointer;
      }
      &::placeholder {
        font-size: 14px;
        font-family: $font-family;
        color: #5a5a5a;
      }
      &:focus {
        outline: none;
      }
    }
  }
}
</style>
