<script setup>
import appleLogo from "@/assets/images/Apple logo.png";
import googleLogo from "@/assets/images/Google.svg";

const stores = [
  { img: appleLogo, top: "Download on the", name: "App Store" },
  { img: googleLogo, top: "Get it on", name: "Google Play" },
];
</script>

<template>
  <section class="mobile">
    <div class="mobile__content container">
      <div class="mobile__content-left">
        <h1 class="mobile__content-left-title">Download Our <span>Mobile App</span></h1>

        <p class="mobile__content-left-text">
          It's all at your fingertips -- the restaurants you love. Find the right
          food to suit your mood, and make the first bite last. Go ahead, download
          app and get 50% discount
        </p>

        <div class="mobile__content-left-last">
          <a v-for="s in stores" :key="s.name" href="#" class="mobile__content-left-last-one">
            <img :src="s.img" alt="" class="mobile__content-left-last-one-img">
            <h3 class="mobile__content-left-last-one-title">
              <span>{{ s.top }}</span>{{ s.name }}
            </h3>
          </a>
        </div>
      </div>

      <div class="mobile__content-right"></div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.mobile {
  margin: 150px 0 50px;

  &__content {
    display: flex;
    flex-wrap: wrap;
    gap: clamp(30px, 8vw, 150px);
    align-items: center;
    justify-content: center;

    &-left {
      max-width: 550px;

      &-title {
        font-weight: 500;
        font-size: 36px;
        line-height: 139%;
        color: #363853;

        span { color: #ff7a50; }
      }

      &-text {
        font-size: 20px;
        line-height: 150%;
        color: #363853;
        opacity: 0.9;
        margin: 15px 0 25px;
      }

      &-last {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;

        &-one {
          display: flex;
          align-items: center;
          gap: 8px;
          background: #0c0d10;
          border-radius: 7px;
          border: 1px solid #a6a6a6;
          padding: 8px 12px;
          color: #fff;
          text-decoration: none;
          transition: transform 0.3s;

          &:hover { transform: translateY(-3px); }
        }

        &-one-img { width: 23px; height: 25px; }

        &-one-title {
          display: flex;
          flex-direction: column;
          color: #fff;
          font-size: 18px;
          line-height: 1.1;

          span { font-size: 14px; opacity: 0.8; }
        }
      }
    }

    &-right {
      width: 100%;
      max-width: 400px;
      aspect-ratio: 1;
      background: url("@/assets/images/iPhone.png") no-repeat center / contain;
    }
  }
}

@media (max-width: 768px) {
  .mobile {
    margin-top: 80px;

    &__content {
      flex-direction: column;
      text-align: center;

      &-left {
        &-title { font-size: 28px; }
        &-text { font-size: 17px; }
        &-last { justify-content: center; }
      }

      &-right { max-width: 280px; }
    }
  }
}
</style>