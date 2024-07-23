<script setup>
defineProps({
  info: {
    type: Object,
    required: true,
  }
})
</script>

<template>
  <div class="hero-stat">
    <div class="hero-stat__number"><strong>{{ info.amount }}</strong></div>
    <p class="hero-stat__description">{{ info.description }}</p>
  </div>
</template>

<style lang="scss">
.hero-stat {
  border: 1px solid $dark-30;
  border-radius: $radius;
  padding: 35px 40px 40px;
  background-color: $dark-80;

  &__number {
    margin-bottom: 10px;
    font-size: 60px;
    line-height: 70.44px;
    letter-spacing: -0.04em;
    color: $primary;
  }

  &__description {
    max-width: 240px;
  }

  @include break($lg) {
    padding: 30px;

    &__number {
      font-size: 40px;
      line-height: 47px;
    }

    &__description {
      max-width: none;
    }
  }
}
</style>
