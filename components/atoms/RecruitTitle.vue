<template>
  <div>
    <h2>{{ name }}</h2>
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
    font-size: 4rem;
    font-weight: normal;
    font-family: "Ropa Sans", sans-serif;
    margin-bottom: 0.25em;
    text-align: center;
    position: relative;
  }
  p {
    margin-bottom: 80px;
    text-align: center;
    font-family: "Ropa Sans", sans-serif;
    font-weight: 100;
    letter-spacing: .03em;
    font-size: 1.2rem;
  }
</style>
