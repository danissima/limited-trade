<script setup>
defineProps({
  info: {
    type: Object,
    required: true
  },
})
</script>

<template>
  <div class="history-item">
    <div class="history-item__period"><b>{{ info.period }}</b></div>
    <p class="history-item__description">{{ info.description }}</p>
  </div>
</template>

<style lang="scss">
.history-item {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  &__period {
    margin-bottom: 30px;
    box-shadow: 0 0 0 20px var(--color-dark-100);
    border-radius: 50px;
    padding: 20px 30px;
    background-color: var(--color-primary);
    font-size: 22px;
    line-height: 22px;
  }

  @include break($lg) {
    align-items: center;
    text-align: center;

    &__period {
      margin-bottom: 10px;
      box-shadow: none;
      padding: 10px 24px;
      font-size: 18px;
      line-height: 18px;
    }
  }
}
</style>
