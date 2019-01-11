<template>
  <div>
    <Title name="ABOUT US" />
    <AboutOverview />
    <AboutContent
      mission="PHOLOSOPHY"
      order="odd"
      name="EXPERIENCE×3" sub="立体的な価値が、展望を生む"
      img="img-about-philosophy.png"
      v-bind:paragraphs="[
      'panoramaが最も大切にしているフィロソフィー。',
      'それが、「Experience3（エクスペリエンス・キューブ」です。',
      '　',
      '①エンドユーザーが感じる体験',
      '②クライアントとの体験',
      '③自身の体験',
      '　',
      'これら3つの”Experience”を立体的に組み合わせることが、',
      '私たちの仕事の真価です。'
      ]"
    />
    <AboutContent
      mission="VISION"
      order="even"
      name="EXPERIENCE EXPLORER" sub="経験の探求者であること"
      v-bind:paragraphs="[
      '私たちがまず提供するのは、経験にもとづく理論と意志。',
      'クライアントのビジネスに最高の結果をもたらすために、',
      '常に時代のトレンドに独自の経験と実績を取り入れ、',
      'ブランド視点・生活者視点の両面から、新たなクリエイティブを生み出します。',
      '経験を伴わない知識だけでは、人の心は動かせません。',
      'だからこそ、私たちのビジョンは自らが常に経験（体験）の探求者であることです。'
      ]"
    />
    <CompanyInformation />
    <Client />
  </div>
</template>

<script>
  import Title from '~/components/atoms/Title'
  import AboutOverview from '~/components/atoms/AboutOverview'
  import AboutContent from '~/components/molecules/AboutContent'
  import CompanyInformation from '~/components/molecules/CompanyInformation';
  import Client from '~/components/molecules/Client';
  export default {
    components : {
      CompanyInformation, Client,
      Title, AboutOverview, AboutContent
    }
  }
</script>

<style lang="scss">
</style>
