<script setup>
const items = [
  { img: "Rectangle.1.png", name: "Blaze Pizza", time: "11.00 AM - 10.00 PM" },
  { img: "Rectangle.2.png", name: "Pizza Ranch", time: "09.00 AM - 10.00 PM" },
  { img: "Rectangle.3.png", name: "Dion’s Pizza Hut", time: "10.00 AM - 12.00 PM" },
  { img: "Rectangle.4.png", name: "Royel Burger", time: "11.00 AM - 10.00 PM" },
  { img: "Rectangle.5.png", name: "KFC Restaurant", time: "09.00 AM - 10.00 PM" },
  { img: "Rectangle.6.png", name: "Star Food", time: "10.00 AM - 12.00 PM" },
];

const getImg = (name) => new URL(`../assets/images/${name}`, import.meta.url).href;
</script>

<template>
  <section class="TopFood">
    <h1 class="TopFood__title">Top Food <span>restaurant</span></h1>

    <div class="TopFood__content container">
      <article v-for="item in items" :key="item.name" class="TopFood__content-box">
        <img :src="getImg(item.img)" :alt="item.name" class="TopFood__content-box-img">
        <h2 class="TopFood__content-box-title">{{ item.name }}</h2>

        <div class="TopFood__content-box-last">
          <img src="@/assets/images/timer%201.svg" alt="time" class="TopFood__content-box-last-time">
          <span class="TopFood__content-box-last-text">{{ item.time }}</span>
          <img src="@/assets/images/Button.svg" alt="open" class="TopFood__content-box-button">
        </div>
      </article>
    </div>
  </section>
</template>

<style scoped lang="scss">
.TopFood {
  margin-top: 150px;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;

  &__title {
    margin-bottom: 30px;
    text-align: center;
    font-weight: 500;
    font-size: 36px;
    text-transform: capitalize;
    color: #363853;

    span { color: #ff7a50; }
  }

  &__content {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 45px;
    width: 100%;
  }

  &__content-box {
    border-radius: 53px 5px;
    max-width: 361px;
    width: 100%;
    background: #fff;
    padding: 15px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    transition: transform 0.3s, box-shadow 0.3s;

    &:hover {
      transform: translateY(-6px);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.1);
    }

    &-img {
      width: 100%;
      aspect-ratio: 4 / 3;
      object-fit: cover;
      border-radius: 53px 5px 0 0;
    }

    &-title {
      font-weight: 400;
      font-size: 24px;
      color: #363853;
    }

    &-last {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      margin-top: auto;

      &-time { width: 18px; height: 18px; }

      &-text {
        font-weight: 300;
        font-size: 18px;
        color: #363853;
        opacity: 0.9;
      }
    }
  }
}

@media (max-width: 768px) {
  .TopFood {
    margin-top: 80px;
    &__title { font-size: 28px; }
    &__content { gap: 25px; }
    &__content-box { border-radius: 35px 5px; text-align: center; }
    &__content-box-title { font-size: 22px; }
    &__content-box-last { justify-content: center; }
    &__content-box-button { display: none; }
  }
}
</style>