<i18n lang="yaml">
ja:
  siteName: シンプルサイト
  copyright: © {year} {siteName}. All rights reserved.
en:
  siteName: Simple Site
  copyright: © {year} {siteName}. All rights reserved.
</i18n>

<template>
  <footer class="ho-the-footer">
    <HaContainer>
      <div class="footer-content">
        <p class="footer-text">
          {{ t('siteName') }}
        </p>
        <p class="footer-copyright">
          {{ t('copyright', { year: currentYear, siteName: t('siteName') }) }}
        </p>
      </div>
    </HaContainer>
  </footer>
</template>

<script lang="ts">
export default defineComponent({
  name: 'HoTheFooter',
})
</script>

<script lang="ts" setup>
const { t } = useI18n()
const currentYear = computed(() => new Date().getFullYear())
</script>

<style scoped lang="scss">
.ho-the-footer {
  margin-top: auto;
  padding: 2rem 0;
  color: white;
  background: #2d3748;
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;

  text-align: center;
}

.footer-text {
  margin: 0;
  font-weight: 600;
}

.footer-links {
  display: flex;
  gap: 2rem;
}

.footer-link {
  font-size: 0.9rem;
  color: rgb(255 255 255 / 80%);
  text-decoration: none;
  transition: color 0.2s;

  &:hover {
    color: white;
  }
}

.footer-copyright {
  margin: 0;
  font-size: 0.875rem;
  color: rgb(255 255 255 / 60%);
}
</style>
