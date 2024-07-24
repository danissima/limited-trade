<script setup>
import AppContainer from '@/components/AppContainer.vue'
import AppButton from '@/components/AppButton.vue'
import HeroStat from '@/components/HeroStat.vue'

const stats = [
  {
    amount: '35 +',
    description: 'Highly qualified experts in sales, logistics and marketing',
  },
  {
    amount: '10 +',
    description: 'Formal distribution agreements',
  },
  {
    amount: '1 000 +',
    description: 'Over a thousand product suppliers working with us',
  },
]
</script>

<template>
  <section class="hero">
    <div class="hero__bg" />
    <AppContainer>
      <div class="hero__content">
        <h1>
          Full range of&nbsp;distribution&nbsp;services for&nbsp;manufacturers and startups from Europe and&nbsp;Asia
        </h1>
        <p>Organise the expansion of your business into new markets</p>
        <AppButton size="large" kind="secondary" href="#contact" is-link>
          Get a commercial offer
        </AppButton>
      </div>
      <div class="hero__stats">
        <HeroStat v-for="stat in stats" :key="stat.description" :info="stat" />
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.hero {
  --padding-top: 180px;
  --content-height: 960px;
  position: relative;
  padding-top: var(--padding-top);

  &__bg {
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    width: 100%;
    height: calc(var(--content-height) + var(--padding-top));
    background-image: url('/images/bg-desktop.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;

    &::after {
      content: '';
      display: block;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image:  linear-gradient(to bottom, transparent 75%, $dark-100 100%);
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
    width: 100%;
    height: var(--content-height);
    max-width: 875px;
    text-align: center;

    p {
      margin: 30px 0 60px;
      font-size: 20px;
      line-height: 23.48px;
    }
  }

  &__stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
  }

  @include break($lg) {
    --content-height: auto;

    &__bg {
      height: 800px;
    }

    &__content {
      margin-bottom: 186px;

      p {
        margin: 20px 0 30px;
        max-width: 220px;
        font-size: 14px;
        line-height: 19.6px;
      }
    }

    .button {
      width: 100%;
    }

    &__stats {
      grid-template-columns: 1fr;
      gap: 20px;
    }
  }

  @include break($md) {
    --padding-top: 78px;

    &__bg {
      background-image: url('/images/bg-mobile.jpg');
    }
  }
}
</style>
