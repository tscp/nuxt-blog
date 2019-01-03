<template>
  <div>
    <Title name="SERVICE" />
    <ServiceContent
      name="BRAND/EC SITE"
      sub="設計＆制作"
      order="odd"
      h3="ウェブサイトを活用してのデジタルブランディング支援"
      v-bind:paragraphs="['アパレルやコスメティックなどのファッションはもちろん、食品、雑貨、店舗など、現代においては、あらゆるモノ・コトに「ブランド」がかかげられています。弊社では、ファッション・ビューティーを中心とした、過去実績をもとに、そこで培った、クリエイティビティ、方法論に基づいた、企画設計、デザイン、構築運用オペレーションを、あらゆる業態のブランドに向けワンストップでご提案しております。世界観やウェブサイトの用途など、方法論はお客様の活用方法により異なるため、弊社では、綿密な打合せを基に、ブランドにあったウェブサイトのご提案し、サイトリリース後はシーズン毎のビジュアル差替をはじめとした運営・更新支援をトータルプロデュースさせていただいております。']"
      v-bind:imgs="['img-branding1.png', 'img-branding2.png', 'img-branding3.png']"
    />
    <ServiceContent
      name="CORPORATE SITE"
      sub="設計＆制作"
      order="even"
      h3="来訪者のニーズに最適化した設計
企業イメージを表現するクリエイティブ訴求"
      v-bind:paragraphs="['コーポレートウェブサイトは、企業情報の最適な伝達や企業イメージの表現の場として、無くてはならない存在です。', '企業としてそれらの情報を的確に伝えるため、サイトの利用目的や求める効果を整理し、ユーザー属性にあわせた情報設計と、来訪目的を満たすため。','求める情報にスムーズにアクセスできる導線設計、コンテンツをわかりやすく表現するデザイン設計などから、最適なコーポレートサイトのご提案を致します。', '　' , 'また、常に最新情報を発信するための更新や、定期的な効果検証の実施が不可欠となります。弊社では、独自のPDCA サイクルに乗っ取った、更新運営支援も実施しております。']"
      v-bind:imgs="['img-corporate1.png', 'img-corporate2.png', 'img-corporate3.png']"
    />
    <ServiceContent
      name="DIGITAL CAMPAIGN"
      sub="設計＆制作"
      order="odd"
      h3="効果的かつ印象的なウェブキャンペーンを
企画～制作までワンストップで支援"
      v-bind:paragraphs="['広告活動において、デジタルが担う役割も年々重要なものとなり、その活用の用途は多岐にわたっております。', '弊社では、デジタルメディア、ソーシャルメディア、また時にはリアルとのクロスメディア戦略を立案し効果的で魅力的なデジタルプロモーションのご提案を致します。']"
      v-bind:imgs="['img-campaign1.png', 'img-campaign2.png', 'img-campaign3.png']"
    />
    <ServiceContent
      name="WEB MEDIA"
      sub="コンサルティング＆運用支援"
      order="even"
      h3="ウェブメディア トータル運営サポート・更新支援"
      v-bind:paragraphs="['常に新しい情報発信と視覚的変化を提供する、各種ウェブメディアにおいて、運営更新のトータルサポートを提供しております。 メディア掲載用の画像制作や更新業務支援をはじめ、ウェブ戦略のご提案やなど、多方面にわたってサポートいたします。']"
      v-bind:imgs="['img-media1.png', 'img-media2.png', 'img-media3.png']"
    />
  </div>
</template>

<script>
  import Title from '~/components/atoms/Title'
  import ServiceContent from "~/components/molecules/ServiceContent";
  export default {
    components : {
      Title, ServiceContent
    }
  }
</script>

<style lang="scss">
</style>
