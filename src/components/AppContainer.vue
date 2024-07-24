<template>
  <div class="container">
    <slot />
  </div>
</template>

<style lang="scss">
.container {
  --container-padding-x: 50px;
  margin: 0 auto;
  width: 100%;
  max-width: $xl;
  padding: 0 var(--container-padding-x);

  @include break($lg) {
    --container-padding-x: 28px;
    max-width: $md;
  }
}
</style>