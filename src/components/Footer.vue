<script setup>
const cols = [
  { title: "Company", links: ["About", "Careers", "Blog"] },
  { title: "Support", links: ["Help Center", "Contact", "Terms"] },
];
</script>

<template>
  <footer class="footer">
    <div class="footer__inner container">
      <div class="footer__brand">
        <a href="#" class="footer__logo">Top<span>Food</span></a>
        <p class="footer__text">Find the best restaurants and get your food delivered fast.</p>
      </div>

      <div v-for="c in cols" :key="c.title" class="footer__col">
        <h4 class="footer__title">{{ c.title }}</h4>
        <a v-for="l in c.links" :key="l" href="#" class="footer__link">{{ l }}</a>
      </div>

      <div class="footer__col">
        <h4 class="footer__title">Contact</h4>
        <span class="footer__link">+998 90 123 45 67</span>
        <span class="footer__link">info@topfood.uz</span>
      </div>
    </div>

    <p class="footer__copy">© 2026 TopFood. All rights reserved.</p>
  </footer>
</template>

<style scoped lang="scss">
.footer {
  background: #363853;
  color: #fff;
  padding: 60px 0 20px;
  margin-top: 80px;

  &__inner {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 40px;
  }

  &__brand { max-width: 300px; }

  &__logo {
    font-size: 28px;
    font-weight: 600;
    color: #fff;
    text-decoration: none;

    span { color: #ff7a50; }
  }

  &__text { margin-top: 12px; line-height: 150%; opacity: 0.8; }

  &__col { display: flex; flex-direction: column; gap: 10px; }

  &__title { font-size: 20px; margin-bottom: 6px; color: #ff7a50; }

  &__link {
    color: #fff;
    opacity: 0.8;
    text-decoration: none;
    transition: opacity 0.3s;

    &:hover { opacity: 1; }
  }

  &__copy {
    text-align: center;
    margin-top: 40px;
    padding-top: 20px;
    border-top: 1px solid rgba(255, 255, 255, 0.15);
    opacity: 0.7;
    font-size: 14px;
  }
}

@media (max-width: 768px) {
  .footer {
    &__inner { flex-direction: column; align-items: center; text-align: center; }
    &__brand { max-width: 100%; }
    &__col { align-items: center; }
  }
}
</style>