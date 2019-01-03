<template>
  <div>
    <Title name="SERVICE" />
    <ServiceTitle name="BRAND/EC SITE" sub="設計＆制作" />
    <ServiceContent
      direction="left"
      h3="ウェブサイトを活用してのデジタルブランディング支援"
      p="アパレルやコスメティックなどのファッションはもちろん、食品、雑貨、店舗など、現代においては、あらゆるモノ・コトに「ブランド」がかかげられています。弊社では、ファッション・ビューティーを中心とした、過去実績をもとに、そこで培った、クリエイティビティ、方法論に基づいた、企画設計、デザイン、構築運用オペレーションを、あらゆる業態のブランドに向けワンストップでご提案しております。世界観やウェブサイトの用途など、方法論はお客様の活用方法により異なるため、弊社では、綿密な打合せを基に、ブランドにあったウェブサイトのご提案し、サイトリリース後はシーズン毎のビジュアル差替をはじめとした運営・更新支援をトータルプロデュースさせていただいております。"
      img1="/images/img-branding1.png"
      img2="/images/img-branding2.png"
      img3="/images/img-branding3.png"
    />
  </div>
</template>

<script>
  import Title from '~/components/atoms/Title'
  import ServiceTitle from '~/components/atoms/ServiceTitle'
  import ServiceContent from "~/components/ServiceContent";
  export default {
    components : {
      Title, ServiceTitle, ServiceContent
    }
  }
</script>

<style>
</style>
