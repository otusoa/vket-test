<template>
  <div class="layout -default">
    <HoTheHeader />
    <main>
      <slot />
    </main>
    <HoTheFooter />
  </div>
</template>

<style lang="scss" scoped>
.layout.-default {
  overflow-x: hidden;
}

main {
  height: 100dvh;
}
</style>
