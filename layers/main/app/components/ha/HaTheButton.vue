<i18n lang="yaml">
ja:
    text: ボタン(初期値を表示しています)
en:
    text: Button(Showing default value)
</i18n>

<template>
  <button class="ha-the-button">
    {{ label || t('text') }}
  </button>
</template>

<script lang="ts">
export default defineComponent({
  name: 'HaTheButton',
})
</script>

<script setup lang="ts">
const { t } = useI18n()

const _props = withDefaults(
  defineProps<{
    label?: string
  }>(),
  {
    label: '',
  },
)
</script>

<style scoped lang="scss">
.ha-the-button {
  cursor: pointer;

  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;

  color: white;

  background: v.$primary-color;

  &:hover {
    background: color.adjust(v.$primary-color, $lightness: -5%);
  }
}
</style>
