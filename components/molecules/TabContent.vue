<template>
  <div>
    <ul class="tab-content">
      <li class="active"><TabButton en="RESEARCH" ja="分析" icon="research" /></li>
      <li><TabButton en="PLANNING" ja="設計" icon="planning" /></li>
      <li><TabButton en="CREATIVE SOLUTION" ja="制作" icon="solution" /></li>
      <li><TabButton en="WEB OPERATION" ja="運用支援" icon="operation" /></li>
    </ul>
    <div class="tab-visuals">
      <TabVisual
        h3="リサーチ・分析"
        p="クライアント及び、ターゲット・ユーザーを理解するためのリサーチ・分析から、本質的なインサイト調査を行います。インサイト調査に基づくストラテジー・クリエイティブ・コンテンツの設計は、より深く意味のあるデジタルコミュニケーションを実現します。"
        class="active"
        bg="bg-visual1.jpg"
      />
      <TabVisual
        h3="企画・設計・プランニング"
        p="ウェブサイト、オンラインストアの企画設計をはじめ、ウェブ事業戦略サポート、プロモーション設計など総合的なウェブソリューションをご提案致します。また、ウェブ連動コンテンツの企画や、付随するマーケティング・リサーチ、メディアバイイング、撮影、キャスティングなどを一環して行うことにより、スムーズかつ効果的なプランニングを実現いたします。"
        bg="bg-visual2.jpg"
      />
      <TabVisual
        h3="クリエイティブ制作"
        p="ファッション・ビューティー・エンターテイメントを中心とした過去実績から得た、独自の方法論に基づき、魅力的かつ洗練されたクリエイティブ制作をご提案いたします。ウェブデザインをはじめ、CI・VIデザイン、また各種POPやカタログ、パッケージ、ポスターなどのグラフィックデザインなど、幅広い領域にて、一貫したデザイン制作を行うことにより、クリエイティブサイドからのブランディング支援を提供。
また、各種デザイン制作〜ウェブサイト、アプリーケーションの構築開発までをワンストップにて行う事が可能です。"
        bg="bg-visual3.jpg"
      />
      <TabVisual
        h3="運用更新支援析"
        p="定常的なウェブコンサルティグをはじめ、ブランドサイト、コーポレートサイト、オンラインストア、ウェブメディア、SNSアカウントなどにおける更新運営支援を実施しております。
ウェブサイトにおいて、日々の効果検証と運用は最も重要なパートとして捉え、独自のPDCAサイクルを循環させたウェブサイトの役割に応じた最適化を目指します。また、定期更新コンテンツの編集更新支援や、オンラインストアの商品登録代行などの更新運営支援も対応いたします。"
        bg="bg-visual4.jpg"
      />
    </div>
  </div>
</template>

<script>
  import TabButton from '~/components/atoms/TabButton'
  import TabVisual from '~/components/atoms/TabVisual'
  export default {
    components: {
      TabButton, TabVisual
    }
  }
</script>

<style lang="scss" scoped>
  .tab-content {
    width: 86%;
    margin: 0 auto;
    border-top: 1px solid #e8e8e8;
    line-height: 1;
    padding: 0;
    display: flex;

    li {
      list-style: none;
      width: 25%;
      color: #7f7f7f;
      fill: #7f7f7f;
      transition: all 0.4s;

      &::after {
        content: '';
        display: block;
        height: 5px;
        transition: all 0.4s;
      }

      &.active, &:hover {
        color: #000;
        fill: #000;

        &::after {
          background-color: #000;
        }
      }
    }
  }
  .tab-visuals {
    width: 100%;
    height: 412px;
    background-color: #000;
    position: relative;
    color: #fff;
    div {
      width: 95%;
      height: 352px;
      margin: 0 auto;
      padding: 60px 0 0 5%;
      background-size: auto, 412px;
      box-sizing: content-box;
      position: absolute;
      z-index: -1;
      opacity: 0;
      transition: all 0.4s;
    }
    .active {
      opacity: 1;
      z-index: 2;
    }
  }
</style>
