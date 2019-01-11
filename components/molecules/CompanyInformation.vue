<template>
  <div class="company-information">
    <article>
      <h4>COMPANY<br>INFORMATION</h4>
      <div class="text-block">
        <DefinitionList dt="COMPANY NAME"
                        dd="株式会社パノラマ" />
        <DefinitionList dt="OFFICE"
                        dd="TOKYO HEAD OFFICE<br>
                            〒150-0034 東京都渋谷区代官山町9-10 SodaCCo 3T05<br>
                            <a class='googlemap' href='https://goo.gl/maps/sqJ2Ddmoddw' target='_blank'>Google Maps</a><br>
                            TEL: 03-6455-1030 / FAX: 03-6455-1031<br><br>
                            OKINAWA OFFICE<br>
                            〒900-0004 沖縄県那覇市銘苅2-5-14 コンフォート石山2nd 302<br>
                            <a class='googlemap' href='https://goo.gl/maps/rWye9sKs3sB2' target='_blank'>Google Maps</a><br>
                            TEL: ‭098-917-2644" />
        <DefinitionList dt="START"
                        dd="2010年11月<br>
(※2016年7月1日 株式会社コムリエより社名変更)" />
        <DefinitionList dt="CAPITAL"
                        dd="7,500,000円" />
        <DefinitionList dt="EXECUTIVE"
                        dd="代表取締役CEO　　樋口 聖<br>
                            代表取締役COO　　牧野秀人<br>
                            取締役CCO　　　　三矢展也<br>
                            取締役　　　　　　小俣 卓充<br>
                            取締役　　　　　　今井 誠之" />
        <DefinitionList dt="MEMBER"
                        dd="25名" />
        <DefinitionList dt="ADVISER"
                        dd="顧問弁護士　：井上辰規(あかね法律事務所)<br>
                            顧問税理士　：和田大志(税理士法人 リライアンス)<br>
                            顧問社労士　：林直子(ベカス労務管理サポート)" />
        <DefinitionList dt="TRADING BANK"
                        dd="三井住友銀行 渋谷駅前支店<br>
                            西武信用金庫 渋谷営業部" />
      </div>
    </article>
  </div>
</template>

<script>
  import DefinitionList from '~/components/atoms/DefinitionList'
  export default {
    components: {
      DefinitionList
    }
  }
</script>

<style lang="scss" scoped>
  .company-information {
    background-color: #f2f2f2;
    article {
      width: 86%;
      margin: 0 auto;
      padding: 60px 0;
      display: flex;
    }
    h4 {
      width: 47%;
      height: auto;
      display: inline-block;
      font-family: "Ropa Sans", sans-serif;
      font-size: 4.8rem;
      font-weight: normal;
      line-height: 1.1;
      letter-spacing: .1em;
      text-align: left;
    }
    .text-block {
      width: 53%;
    }
  }
</style>
