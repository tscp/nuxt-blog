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
    <div class="more-btn">
      <a href="/works/">VIEW MORE OUR WORKS</a>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['posts']
  }
</script>

<style lang="scss" scoped>
  h3 {
    width: 100%;
    height: auto;
    padding: 80px 0;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    letter-spacing: 0.2em;
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
  .more-btn {
    padding-top: 65px;
    padding-bottom: 65px;
    text-align: center;
    a {
      color: #828282;
      font-size: 2rem;
      font-family: "Ropa Sans", sans-serif;
      line-height: 1;
      text-align: center;
      text-decoration: none;
    }
  }
</style>
