<template>
  <div class="tab-visual">
    <h3>{{ h3 }}</h3>
    <p>{{ p }}</p>
    <div class="bg-image" :style="'background-image:url(/assets/images/'+bg+')'"></div>
  </div>
</template>

<script>
  export default {
    props : ['h3', 'p', 'bg'],
    data () {
      return {
        value: 'bg'
      }
    }
  }
</script>

<style lang="scss" scoped>
  .bg-image {
    background-repeat: no-repeat;
    background-size: 68%;
    background-position: right top;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
    &::before {
      content: '';
      background-image: url('/static/assets/images/bg-main-grad.png');
      display: block;
      width: 100%;
      height: 100%;
    }
  }
  h3 {
    font-size: 3rem;
    margin-bottom: 6px;
    line-height: 1.5;
  }
  p {
    font-size: 1.2rem;
    line-height: 1.9;
    margin-bottom: 36px;
    width: 50%;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
</style>
