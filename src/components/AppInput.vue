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
    border: 1px solid $dark-30;
    border-radius: $radius;
    width: 100%;
    padding: 30px;
    background-color: $dark-80;
    transition: border-color $transition;
    font-size: 16px;
    line-height: 18.78px;
    letter-spacing: -0.02em;
    color: $white;

    &::placeholder {
      color: rgba($white, .4);
    }

    &:hover {
      border-color: $white;
    }

    &:focus{
      border-color: $primary;
    }
  }
}
</style>
