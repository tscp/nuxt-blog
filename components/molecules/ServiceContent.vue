<template>
  <div :class="order" class="service-content">
    <article>
      <ServiceTitle :name="name" :sub="sub"/>
      <figure>
        <slideImages class="service" v-bind:slideImages="imgs"/>
        <figcaption>
          <h3>{{ h3 }}</h3>
          <p v-for="p of paragraphs">{{ p }}</p>
        </figcaption>
      </figure>
    </article>
  </div>
</template>

<script>
  import ServiceTitle from '~/components/atoms/ServiceTitle'
  import SlideImages from '~/components/atoms/SlideImages'
  export default {
    props: ['name', 'sub', 'order', 'imgs', 'h3', 'paragraphs'],
    components: {
      ServiceTitle, SlideImages
    }
  }
</script>

<style lang="scss" scoped>
  .service-content {
    article {
      width: 86%;
      margin: 0 auto;
    }
    &:nth-child(odd) {
      background-color: #fbfbfb;
      position: relative;
      z-index: 1;
    }
  }
  h3 {
    margin-bottom: 30px;
    text-align: left;
    font-size: 1.6rem;
    font-weight: bold;
    line-height: 1.5;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
  p {
    font-size: 1.2rem;
    line-height: 1.9;
  }
  figure {
    display: flex;
    justify-content: space-between;
    height: auto;
    figcaption {
      width: 40%;
    }
  }
  .even figure {
    flex-direction: row-reverse;
  }
</style>
