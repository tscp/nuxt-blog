<template>
  <div>
    <Header/>
    <!--nuxt-link to="/" class="button--grey">トップへ戻る</nuxt-link-->
    <h1>WORKS</h1>
    <div class="works">
      <ul class="sort">
        <li>ALL<span>全実績</span></li>
        <li>PRODUCT / SERVICE<span>サービス / プロダクト</span></li>
        <li>CORPORATE<span>企業サイト / CI・CV 制作</span></li>
        <li>CAMPAIGN / AD<span>キャンペーン / 広告</span></li>
        <li>OTHER<span>他実績</span></li>
      </ul>
      <ul class="article-list">
        <li v-for="post in posts" :key="post.id">
          <div class="article-image"></div>
          <div class="title">
            <nuxt-link :to="{ name: 'works-slug', params: { slug: post.fields.slug }}">{{ post.fields.title }}
            </nuxt-link>
          </div>
        </li>
      </ul>
    </div>
    <Footer/>
  </div>
</template>

<script>
  // contentfulの宣言
  import {createClient} from '~/plugins/contentful.js'
  // 設定情報の取得
  const client = createClient()

  export default {
    // 変数の宣言
    data () {
      return {
        posts: []
      }
    },
    // データの取得(非同期)
    asyncData ({ env }) {
      // contentfulより記事データを取得
      return client.getEntries({
        // 対象のブログID
        'content_type': env.CTF_BLOG_ID,
        // 最大取得件数
        'limit': 10,
      }).then(entries => {
        // 取得出来たのでindex.vueに返却
        return {
          posts: entries.items
        }
      }).catch(console.error)
    }
  }
</script>

<style lang="scss">
  h1 {
    width: 100%;
    height: auto;
    padding: 80px 0;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    letter-spacing: 0.2em;
    font-size: 24px;
    font-size: 2.4rem;
  }
  .works {
    background-color: #f6f5f6;
    padding-top: 2em;
  }

  .sort {
    display: flex;
    margin: 0 auto;

    border-right: 1px solid #efefef;
    width: 95%;
    padding: 0;
    li {
      list-style: none;
      line-height: 1.8;
      font-weight: bold;
      width: 20%;
      text-align: center;
      border-left: 1px solid #efefef;
      padding: 1.5em 1em;
      span {
        font-size: .6rem;
        font-weight: normal;
        display: block;
      }
    }
  }

  .article-list {
    overflow: hidden;
    padding: 0;
    margin: 20px auto;
    width: 95%;
    list-style: none;
    display: flex;
    justify-content: space-between;
    /*flex-direction: row;*/
    flex-wrap: wrap;

    li {
      background: #fff;
      width: 30.3333%;
      padding: 20px;
      margin: 0 0 3% 0;

      a {
        background: #fff;
        color: #000;
        text-decoration: none;
      }
    }
  }

</style>
