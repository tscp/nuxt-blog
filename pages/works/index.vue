<template>
  <div>
    <!--nuxt-link to="/" class="button--grey">トップへ戻る</nuxt-link-->
    <Title name="WORKS" />
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
          <article>
            <nuxt-link :to="{ name: 'works-slug', params: { slug: post.fields.slug }}">
              <figure class="article-image">
                <img
                  v-if="post.fields.thumbnailImage"
                  :src="post.fields.thumbnailImage.fields.file.url"/>
                <div class="overlay"></div>
                <p class="view-more">VIEW MORE</p>
              </figure>
              <p class="title">{{ post.fields.title }}</p>
              <p class="date">{{ post.fields.releaseEng }}</p>
              <p class="job">{{ post.fields.jobCategory }}</p>
            </nuxt-link>
          </article>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Title from '~/components/atoms/Title'
  // contentfulの宣言
  import {createClient} from '~/plugins/contentful.js'
  // 設定情報の取得
  const client = createClient()

  export default {
    components : {
      Title
    },
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
      letter-spacing: .05em;
      list-style: none;
      line-height: 1.8;
      font-family: "Roboto Condensed", sans-serif;
      font-size: 1.6rem;
      font-weight: 700;
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

  .article-image {
    img {
      width: 100%;
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
      width: 31.3333%;
      margin: 0 0 3% 0;

      a {
        color: #000;
        text-decoration: none;
        position: relative;

        figure {
          overflow: hidden;
        }

        img {
          filter: blur(0);
          transform: scale(1);
          transition: all 0.4s ease-in-out;
        }

        .overlay {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          opacity: 0;
          transition: all 0.4s;
        }

        .view-more {
          color: #fff;
          font-family: "Ropa Sans", sans-serif;
          font-size: 2rem;
          position: absolute;
          top: 46%;
          left: 0;
          width: 100%;
          text-align: center;
          opacity: 0;
          transition: all 0.3s;
          transform: translate3d(0, 16px, 0);
          &:before {
            content: '+';
            margin-right: 16px;
          }
        }

        &:hover {
          img {
            transform: scale(1.3);
            filter: blur(3px);
          }
          .overlay {
            opacity: 1;
            background: rgba(0, 0, 0, .75);
          }
          .view-more {
            opacity: 1;
            transform: translate3d(0, 0, 0);
          }
        }

      }
    }

    p {
      display: inline-block;
      font-family: "Roboto", sans-serif;
      font-weight: 400;
      font-size: 1.3rem;
      letter-spacing: 0.05em;
      text-decoration: none;
      padding: 10px 0 8px;
      &.title {
        font-family: "Roboto Condensed", sans-serif;
        font-weight: 700;
        font-size: 1.5rem;
        border-bottom: 1px solid #e2e2e2;
        line-height: 1.3;
        letter-spacing: .1em;
        width: 100%;
      }
      &.date {
        width: 21%;
        float: left;
        border-right: 1px solid #e2e2e2;
      }
      &.job {
        width: 74%;
        float: right;
      }
    }

  }

</style>
