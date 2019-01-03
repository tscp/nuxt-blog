<template>
  <div>
    <h2><span>{{ name }}</span></h2>
    <p>{{ sub }}</p>
  </div>
</template>

<script>
  export default {
    props: ['name', 'sub']
  }
</script>

<style lang="scss" scoped>
  div {
    margin: 0 auto;
    padding-top: 98px;
  }
  h2 {
    letter-spacing: 0.2em;
    font-size: 3rem;
    font-weight: normal;
    font-family: "Ropa Sans", sans-serif;
    margin-bottom: 0.25em;
    text-align: center;
    position: relative;
    &::before {
      content: '';
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      border-top: 1px solid #e8e8e8;
      width: 100%;
      left: 0;
      z-index: -1;
    }
    span {
      background-color: #fff;
      display: inline-block;
      letter-spacing: .2rem;
      padding: 0 1em;
      position: relative;
      z-index: 2;
    }
  }
  p {
    margin-bottom: 80px;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    font-weight: 100;
    letter-spacing: .03em;
    font-size: 1.4rem;
  }
  .even h2 span {
    background-color: #fbfbfb
  }
</style>
