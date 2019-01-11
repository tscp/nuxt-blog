<template>
  <div class="client">
    <article>
      <h4>CLIENT</h4>
      <div class="text-block">
        <ClientList category="FASHION / BEAUTY"
                    v-bind:list="[
                      '伊藤忠ファッションシステム',
                      '株式会社 イミュ株式会社',
                      'エスティー・ローダー 株式会社',
                      'ギャップジャパン 株式会社',
                      '株式会社 栗原',
                      '有限会社 ケイ・アール・エス',
                      '株式会社 ケイト・スペードジャパン',
                      'KENNEL & SCHMENGER JAPAN',
                      '株式会社株式会社',
                      'サンエー・インターナショナル三陽商会',
                      '株式会社株式会社',
                      'JS.WORKS株式会社',
                      'TSIホールディングス株式会社',
                      'TSI ECストラテジー株式会社',
                      'ピーチ・ジョン株式会社',
                      'フィッツコーポレーション株式会社',
                      'フレームワークス株式会社',
                      'ベイクルーズ株式会社',
                      'バロックジャパンリミテッド',
                      'マイケル・コース ジャパン 株式会社',
                      'モロッカンオイルジャパン 株式会社',
                      'Laline JAPAN 株式会社']"
        />
        <ClientList category="AGENCY / PRESS ROOM"
                    v-bind:list="[
                      '株式会社 葵プロモーション',
                      'アッシュ・ペー・フランス 株式会社 (PR01.)',
                      '株式会社 AMS',
                      '株式会社ENJIN (猿人)',
                      '株式会社 オリコム',
                      '株式会社 クロスコミュニケーション',
                      '株式会社 クロスリング',
                      '株式会社 ザ・ゴール',
                      '株式会社 GMPC JAPAN (4k[sik])',
                      '株式会社 新通',
                      '株式会社 W media',
                      '株式会社 デルフィス・インタラクティブ',
                      '有限会社 ドラムカン',
                      '株式会社 トレンダーズ',
                      '電通アイソバー株式会社',
                      '株式会社 博報堂',
                      '株式会社 博報堂プロダクツ',
                      '株式会社 博報堂ＤＹメディアパートナーズ',
                      '株式会社 博報堂アイ・スタジオ',
                      '株式会社 マッキャンエリクソンジャパン'
                    ]" />
        <ClientList category="MEDIA / ENTERTAINMENT"
                    v-bind:list="[
                      '株式会社 ASIA CROSS',
                      '株式会社 LDH models',
                      '株式会社 講談社',
                      '株式会社 集英社',
                      'スターツ出版 株式会社',
                      '株式会社 テレビ朝日ミュージック',
                      '株式会社 フジパシフィック音楽出版',
                      '株式会社 レコチョク'
                    ]" />
        <ClientList category="OTHER"
                    v-bind:list="[
                      '株式会社 APOLLO JAPAN',
                      '株式会社 ICEMONSTER JAPAN',
                      '株式会社 海外需要開拓支援機構',
                      '公益財団法人 現代芸術振興財団',
                      '合同会社 きさいや宇和島',
                      'SUNDAY ISSUE',
                      'TAKU KOBAYASHI DESIGN STUDIO',
                      'デイルズフォード・オーガニック・ジャパン',
                      '株式会社 トランジット・ジェネラル・オフィス',
                      '株式会社 トランジットクルー',
                      '株式会社 D.A.B.PASTRY',
                      '株式会社 BAGUS',
                      'MERCER OFFICE 株式会社',
                      '株式会社 ヤマトキャピタルパートナーズ',
                      'REMY COINTREAU JAPAN 株式会社'
                    ]" />
      </div>
      <p>(一部抜粋 /敬称略・50音順)</p>
    </article>
  </div>
</template>

<script>
  import ClientList from '~/components/atoms/ClientList'
  export default {
    components: {
      ClientList
    }
  }
</script>

<style lang="scss" scoped>
  .client {
    article {
      width: 86%;
      margin: 0 auto;
      padding: 60px 0;
    }
    h4 {
      display: inline-block;
      font-family: "Ropa Sans", sans-serif;
      font-size: 4.8rem;
      font-weight: normal;
      line-height: 1.1;
      letter-spacing: .1em;
      text-align: left;
      margin-bottom: 90px;
    }
    .text-block {
      width: 99%;
      height: auto;
      padding-left: 1%;
      > div {
        margin-top: 40px;
        &:first-child {
          margin-top: 0;
        }
      }
    }
  }
</style>
