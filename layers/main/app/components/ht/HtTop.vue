<i18n lang="yaml">
ja:
  hero: ダミーサイトへようこそ
  description: ちょうど良いぐらいのテクノロジーで、チームでOSSや創作活動をする。(ダミー文章)
  section1: セクション1タイトル
  section1Content: 一言で言うと、「共同創作コミュニティ」です。 私たちの団体は、「みんなで協力して何かを作りたい！」という熱意を持ったメンバーが集まるコミュニティです。 もちろん、その「何か」は曖昧でも良いです。アプリ開発やプログラミングに限定せず、メンバーが「これ作ってみたいね」「面白そうだ！」と盛り上がったアイデアを、協力し合いながら形にしていくことを最も大切にしています。
en:
  hero: Welcome to the Dummy site
  description: Using just the right amount of technology to do OSS and creative activities as a team. (Dummy text)
  section1: Section 1 Title
  section1Content: In a word, it is a "collaborative creation community". Our group is a community of members with a passion for "I want to work together to create something!" Of course, that "something" can be vague. Not limited to app development or programming, we value most the idea of members getting excited about "I want to try making this" or "That sounds interesting!" and shaping it together through cooperation.
</i18n>

<template>
  <div class="ht-top">
    <div class="hero-container">
      <div class="hero-content">
        <h1>{{ t('hero') }}</h1>
        <p>{{ t('description') }}</p>
      </div>
    </div>
    <HaTheSection>
      <h1>{{ t('section1') }}</h1>
      <p>{{ t('section1Content') }}</p>
    </HaTheSection>
  </div>
</template>

<script setup lang="ts">
const { t } = useI18n()
</script>

<style lang="scss" scoped>
@use '@/assets/styles/variables' as v;
@use '@/assets/styles/mixins' as m;

.ht-top {
  width: 100%;
  height: 100dvh;
}

.hero-container {
  max-width: v.$pc-content-medium-width;
  margin: 6rem auto 0;
  padding: 2rem;

  color: #fff;
  text-align: center;

  background: v.$primary-color;

  h1 {
    margin-bottom: 1rem;
  }

  p {
    font-size: 1.25rem;
  }
}
</style>
