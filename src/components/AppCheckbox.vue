<script setup>
import IconCheckmark from './icons/IconCheckmark.vue';

defineProps({
  id: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="checkbox">
    <label class="checkbox__label" :for="id">
      <input v-bind="$attrs" class="checkbox__input" type="checkbox" :id="id" :name="name">
      <div class="checkbox__checkmark">
        <IconCheckmark width="20" height="20" />
      </div>
      <span>
        <slot />
      </span>
    </label>
  </div>
</template>

<style lang="scss">
.checkbox {
  &__label {
    cursor: pointer;
    display: flex;
    max-width: fit-content;
    align-items: start;
    font-size: 12px;
    line-height: 16.8px;
  }

  &__input {
    display: none;
  }

  &__checkmark {
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid $dark-30;
    border-radius: $radius;
    padding: 4px;
    background-color: $dark-80;

    svg {
      opacity: 0;
      transition: opacity $transition, color $transition;
    }
  }

  @include hover {
    &__label:hover &__checkmark svg {
      opacity: .4;
    }
  }

  &__input:checked ~ &__checkmark svg {
    opacity: 1;
    color: $primary;
  }

  &__label > span {
    margin: 7px 0 0 20px;
  }

}
</style>
