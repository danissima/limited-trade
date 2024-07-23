<template>
  <div class="container">
    <slot />
  </div>
</template>

<style lang="scss">
.container {
  margin: 0 auto;
  width: 100%;
  max-width: $xl;
  padding: 0 50px;

  @include break($lg) {
    max-width: $md;
    padding: 0 28px;
  }
}
</style>