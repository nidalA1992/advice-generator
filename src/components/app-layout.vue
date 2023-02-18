<template>
  <div class="background">
    <slot />
  </div>
</template>

<style lang="scss" scoped>
.background {
  display: flex;
  padding-inline: 20px;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
