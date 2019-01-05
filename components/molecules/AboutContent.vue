<template>
  <div :class="order" class="about-content">
    <article>
      <AboutSectionTitle :mission="mission" />
      <div v-if="img">
        <figure>
          <img :src="'/assets/images/'+img"/>
          <figcaption>
            <AboutTitle :name="name" :sub="sub"/>
            <p v-for="p of paragraphs">{{ p }}</p>
          </figcaption>
        </figure>
      </div>
      <div v-else>
        <AboutTitle :name="name" :sub="sub"/>
        <p v-for="p of paragraphs">{{ p }}</p>
      </div>
    </article>
  </div>
</template>

<script>
  import AboutTitle from '~/components/atoms/AboutTitle'
  import AboutSectionTitle from '~/components/atoms/AboutSectionTitle'
  export default {
    props: ['mission', 'name', 'sub', 'order', 'h3', 'img', 'paragraphs'],
    components: {
      AboutTitle, AboutSectionTitle
    }
  }
</script>

<style lang="scss" scoped>
  .about-content {
    article {
      width: 86%;
      margin: 0 auto;
      min-height: 550px;
      padding: 60px 0;
    }
    &.odd  {
      background-color: #34333a;
      color: #fff;
      position: relative;
      z-index: 1;
    }
    &.even {

    }
  }
  h2 {
    margin-bottom: 30px;
    text-align: left;
    font-size: 1.6rem;
    font-weight: bold;
    line-height: 1.5;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
  p {
    font-size: 1.4rem;
    line-height: 1.71429;
    white-space: pre-wrap;
    word-wrap: break-word;
    margin-bottom: 7px;
  }
  figure {
    display: flex;
    justify-content: space-between;
    height: auto;
    text-align: center;
    img {
      width: auto;
      height: 100%;
      margin: 0 auto;
    }
    figcaption {
      padding-left: 50px;
      width: 50%;
      text-align: left;
    }
  }
  .even figure {
    flex-direction: row-reverse;
  }
</style>
