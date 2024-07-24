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
  transition: color var(--transition), border-color var(--transition), background-color var(--transition);
  letter-spacing: -0.01em;
  font-weight: 700;

  &_outline {
    border: 1px solid var(--color-white-alpha-20);

    @include hover {
      &:hover {
        border-color: var(--color-white);
      }
    }

    &:active {
      border-color: var(--color-primary);
      color: var(--color-primary);
    }
  }

  &_secondary {
    background-color: var(--color-white);
    color: var(--color-dark-50);

    @include hover {
      &:hover {
        background-color: var(--color-primary);
        color: var(--color-white);
      }
    }

    &:active {
      background-color: var(--color-primary-darken-10);
      color: var(--color-white);
    }
  }

  &_primary {
    background-color: var(--color-primary);
    color: var(--color-white);

    @include hover {
      &:hover {
        background-color: var(--color-primary-lighten-10);
      }
    }

    &:active {
      background-color: var(--color-primary-darken-10);
    }
  }

  &_small {
    font-size: 14px;
    line-height: 16.44px;
  }

  &_medium {
    padding: 30px 64px;
    font-size: 16px;
    line-height: 18.78px;
  }

  &_large {
    padding: 30px 80px;
    font-size: 20px;
    line-height: 23.48px;
  }

  @include break($lg) {
    &_large {
      padding: 24px 48px;
      font-size: 16px;
      line-height: 18.78px;
    }
  }
}
</style>
