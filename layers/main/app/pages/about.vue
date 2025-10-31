<i18n lang="yaml">
ja:
  aboutSection: セクション1タイトル
  aboutSectionContent: 一言で言うと、「共同創作コミュニティ」です。 私たちの団体は、「みんなで協力して何かを作りたい！」という熱意を持ったメンバーが集まるコミュニティです。 もちろん、その「何か」は曖昧でも良いです。アプリ開発やプログラミングに限定せず、メンバーが「これ作ってみたいね」「面白そうだ！」と盛り上がったアイデアを、協力し合いながら形にしていくことを最も大切にしています。
en:
  aboutSection: Section 1 Title
  aboutSectionContent: In a word, it is a "collaborative creation community". Our group is a community of members with a passion for "I want to work together to create something!" Of course, that "something" can be vague. Not limited to app development or programming, we value most the idea of members getting excited about "I want to try making this" or "That sounds interesting!" and shaping it together through cooperation.
</i18n>

<template>
  <HaTheSection>
    <h1>{{ t('aboutSection') }}</h1>
    <p>{{ t('aboutSectionContent') }}</p>
  </HaTheSection>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default',
})

const { t } = useI18n()
</script>
