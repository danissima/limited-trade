<script setup>
import { computed } from 'vue'

const props = defineProps({
  kind: {
    type: String,
    required: false,
    default: 'primary',
    validator(value) {
      return ['primary', 'secondary', 'outline'].includes(value)
    }
  },

  size: {
    type: String,
    required: false,
    default: 'medium',
    validator(value) {
      return ['small', 'medium', 'large'].includes(value)
    }
  },

  isLink: {
    type: Boolean,
    required: false,
    default: false,
  }
})

const classes = computed(() => {
  return {
    'button': true,
    [`button_${props.kind}`]: !!props.kind,
    [`button_${props.size}`]: !!props.size,
  }
})
</script>

<template>
  <button v-if="!isLink" :class="classes" type="button">
    <slot />
  </button>
  <a v-else :class="classes">
    <slot />
  </a>
</template>

<style lang="scss">
.button {
  border-radius: 10px;
  padding: 20px 40px;
  transition: color $transition, border-color $transition, background-color $transition;
  letter-spacing: -0.01em;
  font-weight: 700;

  &_outline {
    border: 1px solid rgba($white, .2);

    &:hover {
      border-color: $white;
    }
  }

  &_small {
    font-size: 14px;
    line-height: 16.44px;
  }
}
</style>
