<template>
  <div class="layout -top">
    <HoTheHeader />
    <slot />
    <HoTheFooter />
  </div>
</template>

<style lang="scss" scoped>
@use '@/assets/styles/variables' as v;

.layout.-top {
  overflow-x: hidden;
}
</style>
