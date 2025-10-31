<i18n lang="yaml">
ja:
  mainlogo: ロゴ名サービス名
  language:
    ja: 日本語
    en: English
en:
  mainlogo: logo name
  language:
    ja: 日本語
    en: English
</i18n>

<template>
  <header class="ho-the-header">
    <div class="logo-container">
      <NuxtLink :to="localePath('/')">
        {{ t('mainlogo') }}
      </NuxtLink>
    </div>

    <button
      class="hamburger-button"
      aria-label="メニュー"
      @click="toggleMenu"
    >
      <span />
      <span />
      <span />
    </button>

    <nav
      class="navigation-content"
      :class="{ 'is-open': isMenuOpen }"
    >
      <HmTheNavigation />

      <div class="language-switcher">
        <NuxtLink
          v-for="loc in availableLocales"
          :key="loc.code"
          :to="switchLocalePath(loc.code)"
          class="lang-link"
          @click="closeMenu"
        >
          {{ t(`language.${loc.code}`) }}
        </NuxtLink>
      </div>
    </nav>
  </header>
</template>

<script lang="ts">
export default defineComponent({
  name: 'HoTheHeader',
})
</script>

<script lang="ts" setup>
const { t, locale, locales } = useI18n()
const switchLocalePath = useSwitchLocalePath()

const availableLocales = computed(() => {
  return locales.value.filter(i => i.code !== locale.value)
})

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const localePath = useLocalePath()
</script>

<style scoped lang="scss">
@use '@/assets/styles/variables' as v;

.ho-the-header {
  position: sticky;
  z-index: v.$zindex-header;
  top: 0;

  display: flex;
  align-items: center;
  justify-content: space-between;

  width: 100%;
  height: v.$header-height-pc;
  padding: 0 40px;

  background-color: v.$white;
  box-shadow: v.$box-shadow;

  @media screen and (width <= 768px) {
    padding: 0 20px;
  }
}

.logo-container {
  font-size: 1.5rem;
  font-weight: bold;

  a {
    color: v.$primary-color;
    text-decoration: none;
  }
}

.hamburger-button {
  cursor: pointer;

  z-index: calc(v.$zindex-header + 1);

  display: none;
  flex-direction: column;
  justify-content: space-between;

  width: 28px;
  height: 20px;
  padding: 0;
  border: none;

  background: transparent;

  &:hover span {
    background-color: v.$primary-color;
  }

  span {
    display: block;

    width: 100%;
    height: 2px;
    border-radius: 2px;

    background-color: v.$gray-2;

    transition: background-color 0.2s;
  }

  @media screen and (width <= 768px) {
    display: flex;
  }
}

.navigation-content {
  display: flex;
  flex-flow: row wrap;
  gap: 2rem;
  align-content: center;
  align-items: center;

  @media screen and (width <= 768px) {
    position: fixed;
    top: v.$header-height-pc;
    right: 0;
    transform: translateX(100%);

    width: 100%;
    max-width: 300px;
    height: calc(100vh - v.$header-height-pc);
    padding: 2rem;

    background-color: v.$white;
    box-shadow: -2px 0 8px rgb(0 0 0 / 10%);

    transition: transform 0.3s ease;

    &.is-open {
      transform: translateX(0);
    }
  }
}

.language-switcher {
  display: flex;
  gap: 1rem;

  @media screen and (width <= 768px) {
    flex-direction: column;
    width: 100%;
  }
}

.lang-link {
  padding: 0.5rem 1rem;
  border: 2px solid v.$primary-color;
  border-radius: 6px;

  font-size: 0.875rem;
  color: v.$gray-2;
  text-align: center;
  text-decoration: none;

  transition: all 0.2s;

  &:hover {
    color: v.$primary-color;
    background-color: rgba(v.$primary-color, 0.1);
  }

  @media screen and (width <= 768px) {
    width: 100%;
    padding: 0.75rem 1rem;
    font-size: 1rem;
  }
}
</style>
