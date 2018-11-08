<template>
  <section class="container">
    <div>
      <h1>記事一覧</h1>
      <nuxt-link to="/" class="button--grey">トップへ戻る</nuxt-link>
      <div class="article-list">
        <ul>
          <li v-for="post in posts" :key="post.id">
            <div class="article-image"></div>
            <div class="title">
              <nuxt-link :to="{ name: 'articles-slug', params: { slug: post.fields.slug }}">{{ post.fields.title }}</nuxt-link>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
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

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.article-list ul {
  padding: 0;
  margin: 0;
  list-style: none;
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  flex-wrap: wrap;
}

.article-list li {
  border: 1px solid #ccc;
  margin: 20px;
  padding: 20px;
}
</style>