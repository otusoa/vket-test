<template>
  <section class="ha-the-section">
    <slot />
  </section>
</template>

<style lang="scss">
@use '@/assets/styles/variables' as v;

.ha-the-section{
  max-width: v.$pc-content-medium-width;
  margin: 5rem auto 0;
  padding: 2rem;

  color: #222;

  background-color: v.$gray-1;

  h1 {
    margin-bottom: 1.5rem;
    font-size: 2rem;
  }

  h2 {
    margin-bottom: 1.5rem;
    font-size: 1.5rem;
  }

  h3 {
    margin-bottom: 1.5rem;
    font-size: 1.25rem;
  }

  p {
    margin-bottom: 1rem;
    font-size: 1rem;
    line-height: 1.6;
  }
}
</style>
