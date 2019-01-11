<template>
  <div>
    <h3>OTHER WORKS</h3>
    <div class="works">
      <ul class="article-list">
        <li v-for="post in posts" :key="post.id">
          <nuxt-link :to="{ name: 'works-slug', params: { slug: post.fields.slug }}">
            <div class="article-image">
              <img
                v-if="post.fields.thumbnailImage"
                :src="post.fields.thumbnailImage.fields.file.url"/>
              <div class="overlay"></div>
              <div class="detail-block">
                <p class="title">{{ post.fields.title }}</p>
                <p class="date">{{ post.fields.releaseEng }}</p>
                <p class="job">{{ post.fields.jobCategory }}</p>
              </div>
            </div>
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="more-btn">
      <a href="/works">VIEW MORE OUR WORKS</a>
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
    width: 100%;
    list-style: none;
    display: flex;
    flex-wrap: wrap;

    li {
      background: #fff;
      width: 33.3333%;
      height: 300px;
      margin: 0;
      overflow: hidden;

      img {
        filter: blur(0);
        transform: scale(1);
        transition: all 0.4s ease-in-out;
        width: 100%;
      }

      .overlay {
        display: block;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        position: absolute;
        transition: all 0.4s;
      }

      a {
        background: #fff;
        color: #000;
        display: block;
        padding: 20px;
        position: relative;
        text-decoration: none;
        width: 100%;
        height: 100%;

        &:hover {
          img {
            transform: scale(1.3);
            filter: blur(3px);
          }
          .overlay {
            opacity: 1;
            background: rgba(0, 0, 0, .75);
          }
          .detail-block {
            transition: all 0.4s ease-out 0.2s;
            opacity: 1;
            transform: translate3d(0,0.0);
            filter:blur(0);
          }
        }
      }
    }
  }

  .detail-block {
    bottom: 24px;
    filter: blur(20px);
    left: 0;
    overflow: hidden;
    opacity: 0;
    padding: 0 5% 3%;
    position: absolute;
    transition: all .2s;
    transform: translate3d(0, 24px, 0);
    width: 100%;

    p {
      color: #fff;
      font-family: "Roboto", sans-serif;
      letter-spacing: .05em;
      text-decoration: none;
    }
    .title {
      border-bottom: solid 1px #fff;
      font-family: "Roboto Condensed", sans-serif;
      font-size: 1.6rem;
      font-weight: 700;
      line-height: 1.25;
      padding-bottom: 0.25em;
    }
    .date {
      font-size: 1.2rem;
      display: table-cell;
      line-height: 1.5;
      padding: 10px 1em 8px 0;
      vertical-align: top;
    }
    .job {
      border-left: solid 1px #fff;
      font-size: 1.2rem;
      display: table-cell;
      padding: 10px 20px 8px 1em;
      vertical-align: top;
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
