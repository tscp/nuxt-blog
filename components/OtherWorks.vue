<template>
  <div>
    <h3>OTHER WORKS</h3>
    <div class="works">
      <ul class="article-list">
        <li v-for="post in posts" :key="post.id">
          <div class="article-image">
            <img
              v-if="post.fields.thumbnailImage"
              :src="post.fields.thumbnailImage.fields.file.url" />
          </div>
          <div class="title">
            <nuxt-link :to="{ name: 'works-slug', params: { slug: post.fields.slug }}">{{ post.fields.title }}
            </nuxt-link>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  // contentfulの宣言
  import {createClient} from '~/plugins/contentful.js'
  // 設定情報の取得
  const client = createClient();

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
  h3 {
    width: 100%;
    height: auto;
    padding: 80px 0;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    letter-spacing: 0.2em;
    font-size: 24px;
    font-size: 2.4rem;
  }

  .article-list {
    overflow: hidden;
    padding: 0;
    margin: 20px auto;
    width: 95%;
    list-style: none;
    display: flex;
    justify-content: space-between;
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
