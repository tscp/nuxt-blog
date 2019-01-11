<template>
  <div>
    <h3><span>{{ mission }}</span></h3>
  </div>
</template>

<script>
  export default {
    props: ['mission']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 0 auto;
  }
  h3 {
    letter-spacing: 0.15em;
    font-size: 1.8rem;
    font-weight: normal;
    font-family: "Ropa Sans", sans-serif;
    margin: 0 auto 85px;
    text-align: center;
    position: relative;
    &::before {
      content: '';
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      border-style: solid;
      border-top-width: 1px;
      border-bottom-width: 1px;
      width: 100%;
      left: 0;
      z-index: -1;
    }
    span {
      display: inline-block;
      letter-spacing: .2rem;
      padding: 0 1em;
      position: relative;
      z-index: 2;
    }
  }
  .odd h3 span {
    background-color: #34333a;
  }
  .even h3 span {
    background-color: #fff;
  }
</style>
