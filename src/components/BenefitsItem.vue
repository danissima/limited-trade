<script setup>
defineProps({
  info: {
    type: Object,
    required: true
  },
})
</script>

<template>
  <div class="benefits-item">
    <div class="benefits-item__icon">
      <component :is="info.icon" width="36" height="36" />
    </div>
    <h3 class="benefits-item__title">{{ info.title }}</h3>
    <p class="benefits-item__description">{{ info.description }}</p>
  </div>
</template>

<style lang="scss">
.benefits-item {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  &__icon {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 28px;
    box-shadow: 0 0 0 8px var(--color-primary-alpha-30);
    border-radius: 50%;
    padding: 14px;
    background-color: var(--color-primary);
  }

  &__title {
    white-space: pre;
  }

  &__description {
    margin-top: 20px;
    font-size: 14px;
    line-height: 21px;
    color: var(--color-white-alpha-70);
  }

  @include break($lg) {
    &__icon {
      margin-bottom: 26px;
      box-shadow: 0 0 0 6px var(--color-primary-alpha-30);
      padding: 10px;

      svg {
        width: 28px;
        height: 28px;
      }
    }

    &__title {
      white-space: unset;
    }

    &__description {
      margin-top: 10px;
    }
  }
}
</style>