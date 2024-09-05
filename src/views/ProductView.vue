
<template>
  <section class="products">
    <div class="container">
      <div class="products-wrapper" id="goods-container">
        <router-link
          class="products-card"
          v-for="item in goodsArray"
          :key="item.id"
          :to="`/item?id=${item.id}`"
        >
          <div class="products-card_image">
            <img :src="getUrl(item.image)" alt="item1" />
          </div>
          <div class="products-card_description">
            <div class="products-card_description-row">
              <h5 class="products-card_description--name">
                {{ item.name }}
              </h5>
            </div>

            <div class="products-card_description-row">
              <p class="products-card_description--text">
                {{ item.description }}
              </p>
            </div>

            <div class="products-card_description-row">
              <div class="products-card_description-controls">
                <button class="btn btn-primary">
                  В корзину
                  <img
                    src="../assets/images/icons/shopping-cart-white.png"
                    alt="shopping-cart-white"
                  />
                </button>

                <span class="products-card_description-controls--price">
                  {{ item.price }} ₽
                </span>
              </div>
            </div>
          </div>
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup>
import { goodsArray } from "../constants/goods";
const getUrl = (name) => {
  return new URL(`../assets/images/goods/${name}`, import.meta.url);
};
</script>
