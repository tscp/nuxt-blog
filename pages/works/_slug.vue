<template>
  <div>
    <h2 class="title">{{ currentPost.fields.title }}</h2>
    <p class="release">{{ currentPost.fields.releaseEng }}</p>
    <ul class="images">
      <li>
        <img
          v-if="currentPost.fields.worksImg1"
          :src="currentPost.fields.worksImg1.fields.file.url" />
      </li>
      <li>
        <img
          v-if="currentPost.fields.worksImg2"
          :src="currentPost.fields.worksImg2.fields.file.url" />
      </li>
    </ul>
    <p class="url"><a :href="currentPost.fields.url">{{ currentPost.fields.url }}</a></p>
    <article>
      <div class="title-block">
        <h3>{{ currentPost.fields.title }}</h3>
        <hr />
        <div>{{ currentPost.fields.mainText }}</div>
      </div>
      <div class="summary-block">
        <dl>
          <dt>CLIENT</dt>
          <dd>{{ currentPost.fields.client }}</dd>
          <dt>AGENCY</dt>
          <dd>{{ currentPost.fields.agency }}</dd>
          <dt>JOB</dt>
          <dd>{{ currentPost.fields.job }}</dd>
          <dt>DATE</dt>
          <dd>{{ currentPost.fields.release }}</dd>
        </dl>
      </div>
    </article>

  </div>
</template>

<script>
// contentfulの宣言
import { createClient } from '~/plugins/contentful.js';
// 設定情報の取得
const client = createClient();

export default {
  // 変数の宣言
  data() {
    return {
      allPosts: [],
      currentPost: [],
    };
  },
  // データの取得(非同期)
  asyncData({ env, params }) {
    return client
      .getEntries({
        content_type: env.CTF_BLOG_POST_TYPE_ID,
      })
      .then((entries) => {
        const posts = entries.items;
        const current = posts.filter(function(item) {
          return item.fields.slug === params.slug;
        });
        return {
          allPosts: posts,
          currentPost: current[0],
        };
      })
      .catch(console.error);
  },
};
</script>

<style lang="scss">
  h2 {
    font-family: "Ropa Sans", sans-serif;
    font-size: 2.4rem;
    letter-spacing: .2em;
    padding: 80px 0 0;
    margin: 90px auto 6px;
    text-align: center;
  }
  .release {
    margin-bottom: 40px;
    text-align: center;
    font-family: "Roboto Condensed", sans-serif;
    font-weight: 400;
    font-size: 1.2rem;
    color: #929292;
    letter-spacing: .2em;
  }
  .url {
    background-color: #333333;
    font-family: "Roboto Condensed", sans-serif;
    font-weight: 400;
    font-size: 1.3rem;
    letter-spacing: .05em;
    padding: 12px 0;
    text-align: center;
    a {
      color: #c0c0c0;
      text-decoration: none;
    }
  }
  .images {
    li {
      list-style: none;
      img {
        width: 100%;
      }
    }
  }
  article {
    display: flex;
    flex-direction: column-reverse;
  }
  .title-block {
    width: 60%;
    display: inline-block;
    line-height: 1.5;
    h3 {
      font-family: "Roboto", sans-serif;
      font-size: 1.8rem;
      font-weight: 400;
      letter-spacing: .05em;
      margin-bottom: 40px;
      text-align: left;
    }
    hr {
      width: 33px;
      height: 1px;
      margin-bottom: 40px;
      border-bottom: solid 1px #e4e4e4;
    }
  }
  .summary-block {
    width: 35%;
    display: inline-block;
    line-height: 1.5;
    dl {
      width: 100%;
      margin-bottom: 40px;
      display: flex;
      flex-wrap: wrap;
      align-content: space-between;
      justify-content: space-between;
      > * {
        letter-spacing: .05em;
        margin-bottom: 40px;
      }
      dt {
        width: 25%;
        font-family: "Roboto Condensed", sans-serif;
        font-size: 1.4rem;
        font-weight: 700;
      }
      dd {
        width: 75%;
        font-family: "Roboto", sans-serif;
        font-size: 1.4rem;
        font-weight: 400;
      }
    }
  }
</style>
