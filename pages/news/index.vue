<template>
  <div>
    <Title name="NEWS" />
    <div>
      <ul class="article-list">
        <li v-for="post in posts" :key="post.id">
          <article>
            <figure class="article-image">
              <img
                v-if="post.fields.image"
                :src="post.fields.image.fields.file.url"/>
            </figure>
            <div class="text-block">
              <div class="date-block">
                <p class="day">{{ post.fields.date }}</p>
                <p class="month-year">{{ post.fields.date }}</p>
              </div>
              <div class="content">
                <h3>{{ post.fields.title }}</h3>
                <div>{{ post.fields.text}}</div>
              </div>
            </div>
          </article>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Title from '~/components/atoms/Title'
  import { createClient } from '~/plugins/contentful.js'
  const client = createClient();

  export default {
    components : {
      Title
    },
    data () {
      return {
        posts: []
      }
    },
    asyncData ({ env }) {
      return client.getEntries({
        content_type: 'news',
        limit: 10,
      }).then(entries => {
        return {
          posts: entries.items
        }
      }).catch(console.error)
    }
  }
</script>

<style lang="scss" scoped>
  .works {
    background-color: #f6f5f6;
    padding-top: 2em;
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
    width: 900px;
    list-style: none;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;

    li {
      margin: 0 auto;
      width: 100%;

      figure {
        line-height: 0;
      }

      a {
        color: #000;
        text-decoration: none;
        position: relative;
      }
    }

    .text-block {
      background-color: #f0f0f0;
      line-height: 1.5;
      padding: 66px 5% 72px;
      margin-bottom: 40px;
      display: flex;
      .content {
        width: 80%;
        h3 {
          font-size: 1.5rem;
          margin-bottom: 18px;
        }
        div, p {
          font-size: 1.2rem;
          line-height: 2;
        }
      }
      .date-block {
        width: 20%;
        display: block;
      }
    }

  }

</style>
