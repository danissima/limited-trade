<script setup>
</script>

<template>
  <div class="input">
    <input v-bind="$attrs" class="input__field">
  </div>
</template>

<style lang="scss">
.input {
  &__field {
    outline: none;
    border: 1px solid var(--color-dark-30);
    border-radius: var(--radius);
    width: 100%;
    padding: 30px;
    background-color: var(--color-dark-80);
    transition: border-color var(--transition);
    font-size: 16px;
    line-height: 18.78px;
    letter-spacing: -0.02em;
    color: var(--color-white);

    &::placeholder {
      color: var(--color-white-alpha-40);
    }

    &:hover {
      border-color: var(--color-white);
    }

    &:focus{
      border-color: var(--color-primary);
    }
  }
}
</style>
