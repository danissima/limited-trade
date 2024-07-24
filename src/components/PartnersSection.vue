<script setup>
import AppContainer from '@/components/AppContainer.vue'
import emblaCarouselVue from 'embla-carousel-vue'

const partners = [
  {
    height: 48,
  },
  {
    height: 55,
  },
  {
    height: 48,
  },
  {
    height: 65,
  },
  {
    height: 50,
  },
  {
    height: 80,
  },
  {
    height: 55,
  },
  {
    height: 60,
  },
]

const [emblaRef] = emblaCarouselVue({
  breakpoints: {
    '(min-width: 768px)': { active: false },
  },
})

const glob = import.meta.glob('@/assets/images/partners/*.png', { eager: true})
const images = Object.entries(glob).map(([key, value]) => value.default)
</script>

<template>
  <section class="partners section section_lighter" id="partners">
    <AppContainer>
      <h2 class="section__title">
        <span>Our trusted partners</span>
      </h2>
      <div ref="emblaRef" class="partners__grid">
        <div class="partners__wrapper">
          <div v-for="(partner, index) in partners" :key="partner.imageSrc" class="partners__slide">
            <div class="partners__item">
              <img :src="images[index]" alt="Partner logo" :height="partner.height">
            </div>
          </div>
        </div>
      </div>
    </AppContainer>
  </section>
</template>

<style lang="scss">
.partners {
  padding: 90px 0 120px;

  h2 {
    text-align: center;
  }

  &__grid {
    overflow: hidden;
  }

  &__wrapper {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
  }

  &__item {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--color-dark-100);
    border-radius: var(--radius);
    height: 168px;
    padding: 0 20px;

    img {
      max-width: 100%;
      object-fit: contain;
    }
  }

  @include break($lg) {
    padding: 40px 0 80px;

    &__wrapper {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @include break($md) {
    &__grid {
      margin: 0 calc(var(--container-padding-x) * -1);
      padding: 0 var(--container-padding-x);
    }

    &__wrapper {
      display: flex;
      gap: 0;
      margin-left: -20px;
    }

    &__slide {
      flex: 0 0 260px;
      min-width: 0;
      padding-left: 20px;
    }

    &__item {
      height: 143px;

      img {
        height: 40px;
      }
    }
  }
}
</style>
