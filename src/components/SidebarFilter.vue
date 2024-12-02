<template>
  <aside class="sidebar">
      <ul class="category-list">
        <li class="category-item main-category">
          <a href="#" class="category-link"
            >Название категории
            <span class="product-count">3</span>
          </a>
        </li>
        <li class="category-item sub-category" v-for="index in 3" :key="index">
          <a href="#" class="category-link">
            <span class="category-name">Название категории</span>
            <span class="product-count">3</span>
          </a>
        </li>
      </ul>

    <div>
      <h2 class="sidebar-title">Цена</h2>
      <div class="range-container">
        <div class="price-input">
          <label class="price-label">от</label>
          <input
            type="text"
            v-model="priceMinValue"
            class="price-field"
            placeholder="0 ₽"
          />
        </div>
        <span class="range-separator">&mdash;</span>
        <div class="price-input">
          <label class="price-label">до</label>
          <input
            type="text"
            v-model="priceMaxValue"
            class="price-field"
            placeholder="0 ₽"
          />
        </div>
      </div>
    </div>

    <div class="filter-section">
      <div class="filter-category">
        <div class="filter-header">
          <span>Бренд</span>
          <button class="clear-button">Очистить</button>
        </div>
        <div class="brand-search-bar">
          <div class="brand-search-container">
            <img
              src="../assets/sidebar-search-logo.svg"
              alt="search logo"
              class="brand-search-logo"
            />
            <input
              type="text"
              v-model="brandSearch"
              placeholder="Поиск"
              class="brand-search-input"
            />
          </div>
        </div>

        <ul class="filter-options">
          <li class="filter-option" v-for="index in 8" :key="index">
            <div>
              <input type="checkbox" :name="'option-' + index" :id="index" />
              <span>Атрибут</span>
            </div>
            <span class="option-count">3</span>
          </li>
        </ul>
      </div>

      <div class="filter-category">
        <div class="filter-header">
          <span>Размер</span>
        </div>
        <ul class="filter-options">
          <li class="filter-option" v-for="index in 6" :key="index">
            <div>
              <input
                type="checkbox"
                :name="'option-' + index"
                :id="index + 100"
              />
              <span>Атрибут</span>
            </div>
            <span class="option-count">3</span>
          </li>
        </ul>
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  data() {
    return {
      priceMinValue: '5500 ₽',
      priceMaxValue: '5500 ₽',
    }
  },
}
</script>

<style scoped lang="scss">
@import '../assets/styles/mixins.scss';
.sidebar {
  width: 280px;
  border: none;
  font-family: Arial, sans-serif;
  font-style: 14px;
  line-height: 16px;

    .category-list {
      list-style: none;
      padding: 0;
      margin: 0;
      margin-top: 24px;

      .category-item {
        transition: background-color 0.3s ease;
        border-radius: 5px;

        &.main-category {
          font-weight: bold;
        }

        &.sub-category {
          padding-left: 20px;
        }

        &:hover {
          background-color: #e2efff;
        }

        .category-link {
          @include flex-center;
          justify-content: space-between;
          padding: 7px;
          color: #333;
          text-decoration: none;
          border-radius: 5px;
          transition: background-color 0.3s ease;

          .category-name {
            flex-grow: 1;
          }

          .product-count {
            margin-left: 10px;
            color: #777;
            font-size: 0.9em;
          }
        }
      }
    }


  .sidebar-title {
    font-family: Arial, sans-serif;
    font-size: 16px;
    line-height: 20px;
    font-weight: 700;
    margin-bottom: 16px;
    margin-top: 28px;
    text-align: center;
  }

  .range-container {
    @include flex-baseline;
    flex-direction: row;

    .price-input {
      position: relative;
      display: inline-flex;
      align-items: center;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 14px;
      height: 36px;
      width: 119px;
      margin-right: 1px;

      .price-label {
        color: gray;
        font-size: 12px;
        margin-right: 6px;
        margin-left: 8px;
        white-space: nowrap;
      }

      .price-field {
        border: none;
        outline: none;
        flex-grow: 1;
        font-size: 16px;
        padding: 0;
        width: 100%;

        &::placeholder {
          color: $gray;
        }
      }
    }

    .range-separator {
      margin-left: 16px;
      margin-right: 16px;
      color: $gray;
      font-size: 10px;
    }
  }

  .filter-section {
    font-family: Arial, sans-serif;
    color: #333;
    margin-top: 28px;

    .filter-category {
      margin-bottom: 20px;

      .filter-header {
        @include flex-center;
        justify-content: space-between;
        font-weight: bold;
        margin-bottom: 10px;

        .clear-button {
          background: none;
          border: none;
          color: $gray;
          text-decoration: underline;
          font-size: 12px;
          line-height: 12px;
          cursor: pointer;
          transition: color 0.3s ease;

          &:hover {
            text-decoration: underline;
            color: $secondary-color;
          }
        }
      }

      .brand-search-bar {
        .brand-search-container {
          @include flex-center;
          height: 36px;
          width: 100%;
          border: 1px solid $gray;
          border-radius: 4px;
          margin-bottom: 16px;

          .brand-search-logo {
            width: 16px;
            height: 16px;
            margin-left: 12px;
          }

          .brand-search-input {
            width: 80%;
            height: 100%;
            border: none;
            padding: 0;
            margin-left: 8px;

            &::placeholder {
              font-size: 14px;
              font-family: Arial, sans-serif;
              color: $gray;
            }

            &:focus {
              outline: none;
            }
          }
        }
      }
    }
  }

  .filter-options {
    max-height: 180px;
    overflow-y: auto;
    list-style: none;
    padding: 0;
    margin: 0;

    .filter-option {
      @include flex-center;
      justify-content: space-between;
      padding: 5px 0;

      .option-count {
        color: gray;
        font-size: 12px;
        margin-right: 16px;
      }
    }

    &::-webkit-scrollbar {
      width: 3px;
    }

    &::-webkit-scrollbar-track {
      background: #ffffff;
    }

    &::-webkit-scrollbar-thumb {
      background: #888;
      border-radius: 10px;
    }

    &::-webkit-scrollbar-thumb:hover {
      background: #555;
    }
  }
}
</style>
