<i18n lang="yaml">
ja:
  home: シンプルサイト
  about: 概要
en:
  home: Simple Site
  about: About
</i18n>

<template>
  <ul>
    <li>
      <NuxtLink :to="localePath('/')">{{ t('home') }}</NuxtLink>
    </li>
    <li>
      <NuxtLink :to="localePath('/about')">{{ t('about') }}</NuxtLink>
    </li>
  </ul>
</template>

<script lang="ts" setup>
const { t } = useI18n()
const localePath = useLocalePath()
</script>

<style scoped lang="scss">
ul {
  display: flex;
  gap: 1rem;

  margin: 0;
  padding: 0;

  list-style: none;

  li {
    a {
      display: inline-block;
      padding: 12px 24px;
      transition: opacity 0.2s;

      &:hover {
        opacity: 0.7;
      }
    }
  }

  @media screen and (width <= 768px) {
    flex-direction: column;
    align-items: start;
  }
}
</style>
