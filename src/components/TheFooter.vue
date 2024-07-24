<script setup>
import AppContainer from '@/components/AppContainer.vue'
</script>

<template>
  <footer class="footer">
    <AppContainer>
      <div class="footer__content">
        <div class="footer__logo">
          <img src="../assets/logo.svg" alt="LDD logo">
          <span>Limited trade development</span>
        </div>
        <div class="footer__links">
          <a class="link" href="#" target="_blank">Privacy policy</a>
        </div>
      </div>
    </AppContainer>
  </footer>
</template>

<style lang="scss">
.footer {
  border-top: 1px solid var(--color-dark-30);
  padding: 60px 0;
  background-color: var(--color-dark-80);

  &__content,
  &__logo,
  &__links {
    display: flex;
    align-items: center;
  }

  &__content {
    justify-content: space-between;
  }

  &__logo {
    img {
      height: 35px;
      margin-right: 30px;
    }

    span {
      font-size: 14px;
      line-height: 16.44px;
    }
  }

  @include break($md) {
    &__content,
    &__logo,
    &__links {
      flex-direction: column;
    }

    &__logo {
      margin-bottom: 40px;

      img {
        margin: 0 0 20px;
      }
    }
  }
}
</style>
