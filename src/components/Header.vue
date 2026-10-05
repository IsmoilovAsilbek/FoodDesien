<script setup>
import { ref } from "vue";

const open = ref(false);
const links = ["Home", "Restaurants", "Menu", "About", "Contact"];
</script>

<template>
  <header class="header">
    <div class="header__inner container">
      <a href="#" class="header__logo">Top<span>Food</span></a>

      <nav class="header__nav" :class="{ 'header__nav--open': open }">
        <a v-for="l in links" :key="l" href="#" class="header__link" @click="open = false">{{ l }}</a>
        <button class="header__btn">Order Now</button>
      </nav>

      <button class="header__burger" aria-label="Menu" @click="open = !open">
        <span></span><span></span><span></span>
      </button>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: #fff;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.06);

  &__inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 16px 15px;
  }

  &__logo {
    font-size: 28px;
    font-weight: 600;
    color: #363853;
    text-decoration: none;

    span { color: #ff7a50; }
  }

  &__nav {
    display: flex;
    align-items: center;
    gap: 30px;
  }

  &__link {
    color: #363853;
    text-decoration: none;
    font-size: 18px;
    transition: color 0.3s;

    &:hover { color: #ff7a50; }
  }

  &__btn {
    background: #ff7a50;
    color: #fff;
    border: none;
    border-radius: 30px;
    padding: 10px 24px;
    font-size: 16px;
    cursor: pointer;
    transition: transform 0.3s;

    &:hover { transform: translateY(-2px); }
  }

  &__burger {
    display: none;
    flex-direction: column;
    gap: 5px;
    background: none;
    border: none;
    cursor: pointer;

    span {
      width: 26px;
      height: 3px;
      background: #363853;
      border-radius: 2px;
    }
  }
}

@media (max-width: 768px) {
  .header {
    &__inner { justify-content: space-between; }
    &__burger { display: flex; }

    &__nav {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      flex-direction: column;
      align-items: center;
      text-align: center;
      gap: 20px;
      padding: 25px 0;
      background: #fff;
      &--open { display: flex; }
    }
  }
}
</style>