<template>
  <section class="container">
    <div class="title">{{ currentPost.fields.title }}</div>
    <div class="text">
      <div class="title">{{ currentPost.fields.mainText }}</div>
    </div>
  </section>
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

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  text-align: left;
}

.title {
  font-size: 30px;
}
</style>