<script setup>
import AppContainer from '@/components/AppContainer.vue'
import AppButton from '@/components/AppButton.vue'
</script>

<template>
  <section class="hero">
    <AppContainer>
      <div class="hero__content">
        <h1>Full range of&nbsp;distribution&nbsp;services for&nbsp;manufacturers and startups from Europe and&nbsp;Asia</h1>
        <p>Organise the expansion of your business into new markets</p>
        <AppButton size="large" kind="secondary" href="#contacts" is-link>
          Get a commercial offer
        </AppButton>
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.hero {
  padding-top: 180px;

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
    width: 100%;
    height: 960px;
    max-width: 875px;
    text-align: center;

    p {
      margin: 30px 0 60px;
      font-size: 20px;
      line-height: 23.48px;
    }
  }

  @include break($lg) {
    padding-top: 78px;

    p {
      margin: 20px 0 30px;
      max-width: 220px;
      font-size: 14px;
      line-height: 19.6px;
    }

    .button {
      width: 100%;
    }
  }
}
</style>
